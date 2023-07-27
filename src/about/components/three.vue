

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';
import * as THREE from 'three';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';
import { OBJLoader } from 'three/examples/jsm/loaders/OBJLoader';
import { SimplifyModifier } from 'three/examples/jsm/modifiers/SimplifyModifier.js';

const canvasContainer = ref(null);
let scene, camera, renderer, controls, headObject;

const canvas = document.body;
const raycaster = new THREE.Raycaster();


const initScene = () => {
  const container = canvasContainer.value;

  scene = new THREE.Scene();

  const loader = new OBJLoader();
  loader.load('./src/assets/3d-models/male_head.obj' , function(object) {
    
    headObject = object
    // Adjust the position, rotation, and scale of the object if needed
    object.position.set(0, 0, 0); // Set the position
    object.rotation.set(25, (Math.PI * 180), 0); // Set the rotation (if needed)
    object.scale.set(1.5, 1.5, 1.5); // Set the scale (if needed)

    const lightLeft = new THREE.PointLight(0xffffff, 1); // White light with intensity 1
    lightLeft.position.set(500, 50, 0); // Position the light
    const lightRight = new THREE.PointLight(0xffffff, 1); // White light with intensity 1
    lightRight.position.set(0, 50, 60); // Position the light
    scene.add(lightLeft);
    scene.add(lightRight);
    const material = new THREE.MeshPhongMaterial({
      color: 0x242424, // Base color of the material
      shininess: 55, // Adjust the shininess (higher value for shinier)
      specular: 0xffffff, // Color of the specular highlight
      wireframe: true,
    });

    // Apply the material to all the meshes in the object
    object.traverse((child) => {
      if (child instanceof THREE.Mesh) {
        child.material = material;
      }
    });
    // Add the loaded object to the scene
    scene.add(object);
  });

  renderer = new THREE.WebGLRenderer({ alpha: true , antialias:true});
  renderer.setSize(container.clientWidth, container.clientHeight);
  renderer.setClearColor(0x000000, 0); // Transparent background

  // Add the renderer to the container
  container.appendChild(renderer.domElement);

  // Create the camera
  camera = new THREE.PerspectiveCamera(
    75,
    container.clientWidth / container.clientHeight,
    0.1,
    500
  );
  camera.position.y = 25
  camera.position.z = 59;

  // Create the OrbitControls
  controls = new OrbitControls(camera, renderer.domElement);
  controls.enablePan = false; // Disable panning
  controls.enableZoom = false; // Enable zooming
};

function calculateMouseNDC(event) {
  const canvasRect = canvas.getBoundingClientRect();
  const mouseX = event.clientX - canvasRect.left;
  const mouseY = event.clientY - canvasRect.top;
  const canvasWidth = canvas.clientWidth;
  const canvasHeight = canvas.clientHeight;
  return new THREE.Vector2((mouseX / canvasWidth) * 1.5 - 1, -(mouseY / canvasHeight) * 1.5 + 1);
}

function checkForIntersections(mouseNDC) {
  raycaster.setFromCamera(mouseNDC, camera);
  return raycaster.intersectObject(headObject, true);
}

const onMouseMove = (event) => {
  if (!canvasContainer.value) return;

  const mouseNDC = calculateMouseNDC(event);
  const intersects = checkForIntersections(mouseNDC);
  console.log(intersects);

  if (intersects.length > 0) {
    const intersection = intersects[0].point;
    headObject.lookAt(intersection);
  }
};

const updateRendererSize = () => {
  const container = canvasContainer.value;
  const width = container.clientWidth;
  const height = container.clientHeight;

  // Update renderer size
  renderer.setSize(width, height);

  // Update camera aspect ratio
  camera.aspect = width / height;
  camera.updateProjectionMatrix();
};

const animate = () => {
  requestAnimationFrame(animate);
  // Rotation based on user interaction
  controls.update();
  if(headObject) { // headObject is the object you want to rotate
    headObject.rotation.y += 0.005; // Change 0.01 to control the speed of rotation
  }
  
  // Default rotation animation
  // You can add any custom animation here if needed

  renderer.render(scene, camera);
};

onMounted(() => {
  initScene();
  animate();
  window.addEventListener('resize', updateRendererSize);
});

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateRendererSize);
});

</script>

<template>
  <div class="relative max-w-56 h-80 md:w-80" ref="canvasContainer">
  </div>
</template>

<style>
/* Add any styles for the Three.js scene container here if needed */
</style>

// const geometry = new THREE.BoxGeometry(1, 1, 1);

  // const edges = new THREE.EdgesGeometry(geometry);

  // const material = new THREE.LineBasicMaterial({ color: 0xFFFFFF });

  // blackBox = new THREE.LineSegments(edges, material);

  // scene.add(blackBox)
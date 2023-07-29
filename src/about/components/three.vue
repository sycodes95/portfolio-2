

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';
import * as THREE from 'three';
import { OrbitControls } from 'three-stdlib/controls/OrbitControls';
import { OBJLoader } from 'three-stdlib/loaders/OBJLoader';

const canvasContainer = ref<HTMLElement | null>(null);
let scene: any, camera: any, renderer: any, controls: any, headObject: any;

const initScene = () => {
  const container = canvasContainer.value;

  scene = new THREE.Scene();

  if(!container) return

  const loader = new OBJLoader();
  loader.load('/src/assets/3d-models/head.obj' , function(object: any) {
    
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
      color: 0x434343, // Base color of the material
      shininess: 55, // Adjust the shininess (higher value for shinier)
      specular: 0xffffff, // Color of the specular highlight
      wireframe: true,
    });

    // Apply the material to all the meshes in the object
    object.traverse((child: any) => {
      if (child instanceof THREE.Mesh) {
        child.material = material;
      }
    });
    // Add the loaded object to the scene
    scene.add(object);
  });

  renderer = new THREE.WebGLRenderer({ alpha: true , antialias:true});3
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
  camera.position.z = 50;

  // Create the OrbitControls
  controls = new OrbitControls(camera, renderer.domElement);
  controls.enablePan = false; // Disable panning
  controls.enableZoom = false; // Enable zooming
};

const updateRendererSize = () => {
  const container = canvasContainer.value;
  if(!container) return
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
  <div class="relative w-72 h-72 max-w-56" ref="canvasContainer">
  </div>
</template>


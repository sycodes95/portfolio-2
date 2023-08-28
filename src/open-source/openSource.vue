<script setup lang="ts">
import Hammer from '../components/icons/Hammer.vue'
import OpenInNew from '../components/icons/OpenInNew.vue';
import CodeRacer1 from '../assets/open-source-images/CodeRacer1.png'
import { onMounted, onUnmounted, ref } from 'vue';

type Project = {
  name: string;
  images: string[];
  description: string;
  tools: string[];
  projectURL: string;
}

const handleProjectClick = (projectURL: string) => window.open(projectURL)

const projects: Project[] = [
  {
    name: "Code Racer",
    images: [CodeRacer1],
    description: "A community project built with Next.js, Tailwind CSS, and TypeScript. Code Racer is a multiplayer coding game where developers can compete against each other to type code in real-time.",
    tools: ['Typescript', 'React', 'Next JS', 'TailwindCSS', 'Postgres'],
    projectURL: "https://code-racer-eight.vercel.app/"
  },
]

const isMdOrAbove = ref(window.innerWidth >= 768);

const handleResize = () => {
  isMdOrAbove.value = window.innerWidth >= 768;
};

onMounted(() => {
  window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
  window.removeEventListener('resize', handleResize);
});
</script>

<template>
  <div class="flex flex-col gap-2 text-green-400 font-exoplane">
    <div id="os-header" class="flex items-center justify-start">
      <Hammer class="w-8 h-8 p-2 text-white bg-black rounded-full border-opacity-10 bg-opacity-80 border-slate-500"/>
      <p class="pl-2 pr-2 text-black font-rockedex">
        <em>OPEN SOURCE</em>
      </p>
    </div>

    <div id="projects-content" class="flex flex-col h-full gap-4 text-xs text-black border-black rounded-sm border-opacity-10 bg-opacity-5 font-rockedex">
      <div class="relative flex gap-4 p-2 transition-colors duration-300 bg-black bg-opacity-0 rounded-sm group hover:cursor-pointer md:hover:bg-opacity-5 max-w-768-flex-col" 
      v-for="(project, index) in projects" :key="index"
      @click="isMdOrAbove && handleProjectClick(project.projectURL)">

        <div class="flex flex-col gap-2">

          <p class="flex items-center gap-2 text-lg font-bold transition-colors duration-300 md:group-hover:text-white hover:cursor-pointer hover:text-white w-fit"
          @click="!isMdOrAbove && handleProjectClick(project.projectURL)">{{ project.name }}<OpenInNew class="w-4 h-4"/>
          </p>

          <div class="flex w-full md:hidden">
            <img class="w-56 border-4 border-black rounded-sm border-opacity-10 grayscale" :src="project.images[0]" alt="project-image-1">
          </div>
          
          <p class="flex flex-wrap rounded-sm ">{{ project.description }}</p>

          <div class="flex flex-wrap gap-2" >
            <p class="p-1 text-xs text-black border border-black border-opacity-75 rounded-sm bg-opacity-80" v-for="(tool, index) in project.tools" :key="index">{{ tool }}</p>
          </div>          

          
        </div>

        <img class="w-32 border-4 border-black rounded-sm border-opacity-10 grayscale h-fit max-w-768-hidden" :src="project.images[0]" alt="project-image-1">

      </div>
      
    </div>
  </div>

</template>

<style scoped>
</style>
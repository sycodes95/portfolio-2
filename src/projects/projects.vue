<script setup lang="ts">
import Hammer from '../components/icons/Hammer.vue'
import RLMechanicPng from '../assets/project-images/rlmechanics.png'
import JobTrackrPng from '../assets/project-images/jobtrackr.png'
import EdgeScoutPng from '../assets/project-images/edgescout.png'
import OnTheBallStats from '../assets/project-images/ontheballstats.png'
import OpenInNew from '../components/icons/OpenInNew.vue';
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
    name: "On The Ball Stats",
    images: [OnTheBallStats],
    description: "Football (soccer) statistics application that displays data for fixtures, leagues, teams and players in a simple way with user friendly UI. ",
    tools: ['React', 'Redux', 'TailwindCSS'],
    projectURL: "https://ontheballstats.com/"
  },
  {
    name: "Job Tracker",
    images: [JobTrackrPng],
    description: "Job application tracker for managing and gaining data driven insights into the users’ job hunting journey. Features sorting, filtering, searching, and data visualizations.",
    tools: ['React', 'TailwindCSS', 'Node Js', 'Postgres'],
    projectURL: "https://jobtrackr.pro/"
  },
  {
    name: "Rocket League Mechanics",
    images: [RLMechanicPng],
    description: "A rocket league mechanic database where you can browse and learn all of the known mechanics players have come up with since launch of the game! ",
    tools: ['Typescript', 'React', 'Redux', 'TailwindCSS', 'Node Js', 'Postgres'],
    projectURL: "https://rlmechanics.com/"
  },
  {
    name: "Edge Scout",
    images: [EdgeScoutPng],
    description: "Trading journal app made to help traders track and refine their strategies with data visualization and analysis features.",
    tools: ['React', 'TailwindCSS', 'Node Js', 'MongoDB'],
    projectURL: "https://edgescout.up.railway.app/"
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
    <div id="projects-header" class="flex items-center justify-end">
      <p class="pl-2 pr-2 text-black font-rockedex">
        <em>PROJECTS</em>
      </p>
      <Hammer class="w-8 h-8 p-2 text-white bg-black rounded-full border-opacity-10 bg-opacity-80 border-slate-500"/>
    </div>

    <div id="projects-content" class="flex flex-col h-full gap-4 text-xs text-black border-black rounded-sm border-opacity-10 bg-opacity-5 font-rockedex">
      <div class="relative flex gap-4 p-2 transition-colors duration-300 bg-black bg-opacity-0 rounded-sm group md:hover:cursor-pointer md:hover:border-opacity-50 md:hover:bg-opacity-5 max-w-768-flex-col" 
      v-for="(project, index) in projects" :key="index" @click="isMdOrAbove && handleProjectClick(project.projectURL)">

        <img class="w-32 border-4 border-black rounded-sm border-opacity-10 grayscale h-fit max-w-768-hidden" :src="project.images[0]" alt="project-image-1">

        <div class="flex flex-col gap-2">
          <p class="flex items-center gap-2 text-lg font-bold transition-colors duration-300 hover:cursor-pointer md:group-hover:text-white hover:text-white text-shadow-black"
          @click="!isMdOrAbove && handleProjectClick(project.projectURL)">
          {{ project.name }}
          <OpenInNew class="w-4 h-4"/>
          </p>

          <div class="flex w-full md:hidden">
            <img class="w-56 border-4 border-black rounded-sm border-opacity-10 grayscale" :src="project.images[0]" alt="project-image-1">
          </div>
          
          <p class="flex flex-wrap rounded-sm ">{{ project.description }}</p>

          <div class="flex flex-wrap gap-2" >
            <p class="p-1 text-xs text-black border border-black border-opacity-75 rounded-sm bg-opacity-80" v-for="(tool, index) in project.tools" :key="index">{{ tool }}</p>
          </div>
        </div>

      </div>
      
      
      
    </div>
  </div>

</template>

<style scoped>
.text-shadow-black :hover{
  text-shadow: 1.5px 1.5px 0px rgba(0, 0, 0, 0.4);
}
</style>
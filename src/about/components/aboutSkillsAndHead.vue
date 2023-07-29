<script setup lang="ts">
import { toolsElements } from "../constants";
import Three from '../components/three.vue'
</script>

<template>
  <div class="relative flex justify-between w-full border-black border-opacity-75">
    <div class="flex flex-col gap-4 md:relative">
      
      <div class="flex flex-col">
        <p class="pl-1 text-lg text-black text-opacity-0 font-black-outline font-exoplane">Skills</p>
        <div class="relative z-10 flex flex-col gap-1 p-2 rounded-sm bg-opacity-5 border-opacity-5 ">
          <div class="absolute top-0 left-0 z-0 w-full h-full backdrop-blur-sm"></div>
          <div v-for="(tool, index) in toolsElements" :key="index"
          class="z-10 flex items-center gap-2 text-xs text-black text-opacity-80">
            <i :class="[tool.class]"></i>
            <p class="">{{ tool.name }}</p>
          </div>
        </div>
      </div>
      
    </div>
    
    <div class="absolute flex justify-center w-full h-full lg:relative">
      <!-- overlay with high z index for mobile users to scroll -->
      <div id="overlay" class="absolute top-0 left-0 z-10 w-full h-full md:hidden"></div>
      <Three class="transition-all duration-1000 hover:cursor-move"/>
      <!-- <ThreeAudioVisual class=""/> -->
    </div>


    <!-- <img class="absolute w-64 opacity-25 -translate-x-3/4 left-3/4" :src="silhoutte" alt="silhoutte"/> -->
  </div>
</template>
<script setup lang="ts">
import silhoutte from '../../assets/images/silhouette.png'
import { toolsElements } from "../constants";
import Three from '../components/three.vue'
import koreanFlag from '../../assets/images/south-korea.png'
import americanFlag from '../../assets/images/united-states-of-america.png'
import OpenInNew from '../../components/icons/OpenInNew.vue'
</script>

<template>
  <div class="relative flex justify-between w-full border-black border-opacity-75">
    <div class="flex flex-col gap-4 md:relative">
      <div class="flex flex-col gap-2">
        <p class="pl-1 text-xl text-black text-opacity-0 font-black-outline font-exoplane">Skills</p>
        <div class="relative z-10 flex flex-col gap-1 p-2 rounded-sm bg-opacity-5 border-opacity-5 ">
          <div class="absolute top-0 left-0 z-0 w-full h-full backdrop-blur-sm"></div>
          <div v-for="(tool, index) in toolsElements" :key="index"
          class="z-10 flex items-center gap-2 text-xs text-black text-opacity-80">
            <i :class="[tool.class]"></i>
            <p class="">{{ tool.name }}</p>
          </div>
        </div>
      </div>

      <div class="flex flex-col gap-2 ">
        <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Languages</p>
        <div class="relative flex flex-col gap-1 p-2 text-xs text-black rounded-sm ">
          <div class="absolute top-0 left-0 z-0 w-full h-full backdrop-blur-sm"></div>
          <div class="z-10 flex items-center gap-2">
            <img class="w-6 h-6" :src="americanFlag" alt="american flag"/>
            <p>English</p>
          </div>
          <div class="z-10 flex items-center gap-2">
            <img class="w-6 h-6" :src="koreanFlag" alt="korean flag"/>
            <p>Korean</p>
          </div>
        </div>
      </div>
      
    </div>
    
    <div class="absolute flex flex-col w-full h-full md:relative">
      <div class="flex justify-end w-full">
        <button class="p-1 text-xs transition-colors duration-300 bg-black border border-black border-opacity-0 rounded-sm bg-opacity-80 hover:bg-opacity-0 hover:text-black hover:border hover:border-black hover:border-opacity-10">
          Github
        </button>
      </div>
    <Three class=""/>

    </div>


    <!-- <img class="absolute w-64 opacity-25 -translate-x-3/4 left-3/4" :src="silhoutte" alt="silhoutte"/> -->
  </div>
</template>
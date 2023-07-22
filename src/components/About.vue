

<script setup lang="ts">
  import silhoutte from '../assets/images/silhoutte.png'
  import comicFrame from '../assets/bg-images/comic-frame.png'
  import Dna from '../components/icons/Dna.vue'
</script>

<template>
  <div class="flex flex-col justify-center w-full">
    <div id="about-header" class="flex items-center">
      
      <Dna class="w-10 h-10 p-2 text-black rounded-sm border-opacity-10 bg-opacity-5 border-slate-500"/>
      <p class="text-black border-black font-rockedex">About</p>
    </div>
    <div class="flex flex-col items-center justify-center w-full rounded-sm">
      <div class="w-full p-4 text-black rounded-sm text-md font-wolves font-rockedex bg-opacity-40">
        - I am a Front End focused full stack developer with a passion for building stuff"
      </div>
      <div class="relative">
        <img class="w-56 opacity-90" :src="silhoutte" alt="silhoutte"/>
        <img class="absolute top-0 w-full opacity-90" :src="comicFrame" alt="comicFrame"/>
      </div>
    </div>
  </div>
</template>

<style scoped>


</style>

<script setup lang="ts">
const firstName: string[] = ['k', 'e', 'v', 'i', 'n']
const lastName: string[] = ['k', 'i', 'm']

const web: string[] = ['w', 'e', 'b']
const developer: string[] = ['d', 'e', 'v','e', 'l', 'o', 'p', 'e', 'r']
</script>

<template>
  <div class="flex items-center justify-center w-full h-full text-6xl font-exoplane ">
    <div class="flex gap-4 text-5xl text-left text-white text-opacity-0 transition-all duration-200 border-dotted vertical-text">
      <p class="font-white-outline">Web</p> 
      <p class="font-white-outline">Developer</p>
      <p class="text-green-400">.</p>
    </div>
    
    <div class="flex gap-4 text-left text-white text-7xl vertical-text">
      <p>kevin</p> 
      <p class="">kim</p>
    </div>
    
  </div>
</template>

<style scoped>
.bg-intro{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
}
.font-exoplane{
  font-family: Exoplane, Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
}
.vertical-text {
  writing-mode: vertical-lr;
}
.text-upright{
  text-orientation: upright;
}
</style>

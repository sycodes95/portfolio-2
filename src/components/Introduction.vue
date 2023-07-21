<script setup lang="ts">
const firstName: string[] = ['k', 'e', 'v', 'i', 'n']
const lastName: string[] = ['k', 'i', 'm']

const web: string[] = ['w', 'e', 'b']
const developer: string[] = ['d', 'e', 'v','e', 'l', 'o', 'p', 'e', 'r']
</script>

<template>
  <div class="flex flex-col justify-center w-full h-full text-5xl font-wolves ">
    <div class="flex gap-4 text-left text-black font-size-name">
      <p class=""><span class="">K</span>EVIN</p> 
      <p class="">KIM</p>
    </div>
    <div class="flex gap-4 text-left text-orange-500 transition-all duration-200 border-dotted font-size-developer">
      <p class="">WEB</p> 
      <p class="">
        <span class="">DEVELOPER</span>
        <span class="text-black outline-none">.</span>
      </p>
    </div>
    
  </div>
</template>

<style scoped>
.bg-intro{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
}

.font-size-name{
  font-size: clamp(4rem, 6vw, 6rem);
}
.font-size-developer{
  font-size: clamp(2.5rem, 3vw, 6rem);
}
.vertical-text {
  writing-mode: vertical-lr;
}
.text-upright{
  text-orientation: upright;
}
</style>

<script setup lang="ts">
const firstName: string[] = ['k', 'e', 'v', 'i', 'n']
const lastName: string[] = ['k', 'i', 'm']

const web: string[] = ['w', 'e', 'b']
const developer: string[] = ['d', 'e', 'v','e', 'l', 'o', 'p', 'e', 'r']
</script>

<template>
  <div class="flex flex-col justify-center w-full h-full p-2 font-exoplane">
    <div class="flex items-center gap-4 text-left text-black text-opacity-0 font-black-outline font-size-name line-height-1">
      <p class=""><span class="">K</span>EVIN</p> 
      <p class="">KIM</p>
    </div>
    <div class="flex gap-4 text-left text-black text-opacity-0 transition-all duration-200 border-dotted font-black-outline font-size-developer">
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
  font-size: clamp(3rem, 6vw, 6rem);
  line-height: 0.8;
}

.font-size-developer{
  font-size: clamp(1.8rem, 4vw, 3rem);
  line-height: 1.2;
}
.vertical-text {
  writing-mode: vertical-lr;
}
.text-upright{
  text-orientation: upright;
}
</style>

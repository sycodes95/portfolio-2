<script setup lang="ts">
import koreanFlag from '../../assets/images/south-korea.png'
import americanFlag from '../../assets/images/united-states-of-america.png'
</script>

<template>
  <div class="flex flex-col gap-4">

    <!-- <div class="flex flex-col ">
      <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Hobbies</p>
      <div class="relative flex gap-1 p-2 text-sm text-black rounded-sm ">
        <i class="fa-solid fa-dumbbell"></i>
        <i class="fa-solid fa-person-running"></i>
        <i class="fa-solid fa-gamepad"></i>
        <i class="fa-solid fa-music"></i>
      </div>
    </div>
     -->
    <div class="flex flex-col ">
      <!-- <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Languages</p> -->
      <div class="relative flex gap-1 p-2 text-xs text-black rounded-sm ">
        <div class="absolute top-0 left-0 z-0 w-full h-full backdrop-blur-sm"></div>
        <div class="z-10 flex items-center gap-2">
          <img class="w-10" :src="americanFlag" alt="american flag"/>
        </div>
        <div class="z-10 flex items-center gap-2">
          <img class="w-10" :src="koreanFlag" alt="korean flag"/>
        </div>
      </div>
    </div>

    

    <!-- <div class="flex flex-col gap-2 ">
      <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane"></p>
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
    </div> -->

   
  </div>
</template>

<style scoped>
</style>

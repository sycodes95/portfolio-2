

<script setup lang="ts">
  import silhoutte from '../assets/images/silhoutte.png'
  import comicFrame from '../assets/bg-images/comic-frame.png'
  import Dna from '../components/icons/Dna.vue'

  const skills = [
    { name: "Typescript", src:  "test"}
  ]
</script>

<template>
  <div class="flex flex-col justify-center w-full gap-2">
    <div id="about-header" class="flex items-center text-black rounded-sm w-fit">
      
      <Dna class="w-10 h-10 p-2 rounded-sm border-opacity-10 bg-opacity-5 border-slate-500"/>
      <p class="pl-2 pr-2 border-l border-black font-rockedex">About</p>
    </div>
    <div class="flex flex-col items-center justify-center w-full gap-4 rounded-sm">

      <div class="w-full p-4 text-xs text-black bg-black border border-black rounded-sm border-opacity-10 bg-opacity-5 ">
        I am a front end focused full stack developer with a passion for building and learning
      </div>

      <div class="relative flex justify-between w-full">
        <div class="flex flex-col gap-4 p-4">
          <div class="flex flex-col gap-2">
            <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Skills</p>
            <div class="flex flex-col gap-1 text-xs text-black rounded-sm bg-opacity-5 border-opacity-10">
              <div>Javaaaaaaaaaaa</div>
              <div>Java</div>
              <div>Java</div>
            </div>
          </div>

          <div class="flex flex-col gap-2">
            <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Languages</p>
            <div class="flex flex-col gap-1 text-xs text-black rounded-sm bg-opacity-5 border-opacity-10">
              <div>English</div>
              <div>Korean</div>
            </div>
          </div>

          <div>
            <p class="ml-2 text-xl text-black text-opacity-0 font-black-outline font-exoplane">Links</p>
            <div class="flex flex-col gap-1 p-4 text-xs text-black bg-black border border-black rounded-sm bg-opacity-5 border-opacity-10">
              <div>Korean</div>
              <div>English</div>
            </div>
          </div>
        </div>
        <img class="absolute right-0 w-64 opacity-30" :src="silhoutte" alt="silhoutte"/>
        <!-- <img class="absolute top-0 w-full opacity-90" :src="comicFrame" alt="comicFrame"/> -->
      </div>
    </div>
  </div>
</template>

<style scoped>


</style>

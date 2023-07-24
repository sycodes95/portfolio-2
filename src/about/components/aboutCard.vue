<script setup>
import silhoutte from '../../assets/images/silhouette.png'
import { toolsElements } from "../constants";
import Three from '../components/three.vue'
</script>

<template>
  <div class="relative flex justify-between w-full border-black border-opacity-75">
    <div class="flex flex-col gap-4">
      <div class="flex flex-col gap-2 p-4 bg-black bg-opacity-5">
        <p class="text-xl text-black text-opacity-0 font-black-outline font-exoplane">Skills</p>
        <div v-for="(tool, index) in toolsElements" :key="index"
        class="flex flex-col gap-1 text-xs text-black rounded-sm bg-opacity-5 border-opacity-10">
          <div class="flex items-center gap-2 text-black">
            <i :class="[tool.class]"></i>
            <p>{{ tool.name }}</p>
          </div>
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
    <div class="flex flex-col items-center w-full h-full">
      <div>test</div>
      <Three class=""/>

    </div>

    <!-- <img class="absolute w-64 opacity-25 -translate-x-3/4 left-3/4" :src="silhoutte" alt="silhoutte"/> -->
  </div>
</template>
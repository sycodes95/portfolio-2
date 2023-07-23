<script setup lang="ts">
import Hammer from '../components/icons/Hammer.vue'
</script>

<template>
  <div class="flex flex-col gap-2 text-green-400 font-exoplane">
    <div id="projects-header" class="flex items-center">
      <Hammer class="w-10 h-10 p-2 text-black rounded-sm border-opacity-10 bg-opacity-5 border-slate-500"/>
      <p class="pl-2 pr-2 text-black border-l border-black font-rockedex">Projects</p>
    </div>

    <div id="projects-content" class="p-2 text-xs text-black border-black rounded-sm border-opacity-10 bg-opacity-5 font-rockedex h-96">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </div>
  </div>

</template>

<style scoped>
</style>
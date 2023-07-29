<script setup lang="ts">
import Link from '../../components/icons/Link.vue'



</script>

<template>

  <div class="flex w-full gap-2">
    <a class="flex items-center h-6 gap-1 p-1 text-xs transition-colors duration-300 bg-black border border-black border-opacity-0 rounded-sm bg-opacity-80 hover:bg-opacity-0 hover:text-black hover:border hover:border-black hover:border-opacity-10"
    href="https://github.com/sycodes95"
    target="_blank">
      <i class="devicon-github-original"></i>
      <p>Github</p>
    </a>
    
    <a class="flex items-center h-6 gap-1 p-1 text-xs transition-colors duration-300 bg-black border border-black border-opacity-0 rounded-sm bg-opacity-80 hover:bg-opacity-0 hover:text-black hover:border hover:border-black hover:border-opacity-10"
    href="https://drive.google.com/file/d/1U4K3tvlx0SibXKBSvG4fUq8StlV9MInh/view?usp=drive_link"
    target="_blank">
      <Link class="w-4 h-4"/>
      <p>Resume</p>
    </a>
  </div>

</template>

<style scoped>
</style>
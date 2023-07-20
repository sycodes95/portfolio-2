<script setup lang="ts">
import Header from './components/Header.vue'
import Introduction from './components/Introduction.vue'
</script>

<template>
  <div class="relative flex flex-col items-center min-h-screen bg-black bg-main">
    <Header class="absolute top-0"/>
    <div id="content" class="grid flex-1 h-full max-w-2xl grid-cols-2">
      
      <Introduction/>
      <div class="flex justify-center whitespace-pre-wrap text-7xl"></div>

    </div>
  </div>
</template>

<style scoped>
.bg-main{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
}
</style>

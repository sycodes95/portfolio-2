<script setup lang="ts">
import Header from './components/Header.vue'
import Introduction from './components/Introduction.vue'
import Projects from './components/Projects.vue';
</script>

<template>
  <div class="relative flex flex-col items-center min-h-screen overflow-x-hidden bg-black bg-main">
    <div id="content" class="flex flex-col w-full h-full max-w-2xl gap-4 pt-16 pl-8 pr-8">
      <Introduction/>
      <Projects/>
    </div>
  </div>
</template>

<style scoped>
/* .bg-main{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
} */
.bg-main{
  background: linear-gradient(rgba(255, 255, 255, 0.75), rgba(252, 254, 255, 0.75)), url(./assets/bg-images/subtle_carbon.webp);
}
</style>

<script setup lang="ts">
import About from './about/about.vue';
import Header from './header/header.vue'
import Introduction from './introduction/introduction.vue'
import Projects from './projects/projects.vue';
import blackWaves from './assets/bg-images/black-and-white-waves.png'
</script>

<template>
  <div class="relative flex flex-col items-center min-h-screen bg-black bg-main">
    <div id="content" class="flex w-full h-full max-w-lg gap-4 pt-12 pl-4 pr-4 md:max-w-4xl max-w-768-flex-col">

      <section id="section-two" class="relative flex flex-col w-full h-full max-w-5xl gap-4">
        <div class="lg:absolute">
          <Introduction/>
          <About/>
        </div>
        
      </section>

      <section id="section-one" class="flex flex-col w-full h-full max-w-5xl gap-4 pt-8">
        <Projects/>
        
      </section>

    </div>
  </div>
</template>

<style scoped>
/* .bg-main{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
} */
.bg-main{
  background: linear-gradient(rgba(255, 255, 255, 0.8), rgba(252, 254, 255, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
}
</style>

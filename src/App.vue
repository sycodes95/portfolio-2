<script setup lang="ts">
import About from './about/about.vue';
import Introduction from './introduction/introduction.vue'
import Projects from './projects/projects.vue';
import OpenSourceProjects from './open-source/openSource.vue'
</script>

<template>
  <div class="flex flex-col items-center min-h-screen bg-black bg-main">
    <div id="content" class="flex w-full max-w-lg min-h-screen gap-8 pt-12 pb-12 pl-4 pr-4 md:max-w-4xl max-w-768-flex-col">

      <section id="section-two" class="flex flex-col justify-center h-full max-w-5xl gap-4 md:sticky top-12 md:w-1/2">
        <div class="h-full">
          <Introduction/>
          <About/>
        </div>
        
      </section>

      <section id="section-one" class="flex flex-col h-full max-w-5xl gap-8 pb-8 overflow-auto md:w-1/2">
        <Projects/>
        <OpenSourceProjects/>
      </section>

    </div> 
  </div>
</template>

<style>
/* .bg-main{
  background: linear-gradient(rgba(20, 26, 33, 0.8), rgba(20, 26, 33, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
} */
.bg-main{
  background: linear-gradient(rgba(255, 255, 255, 0.8), rgba(252, 254, 255, 0.8)), url(./assets/bg-images/subtle_carbon.webp);
}
</style>

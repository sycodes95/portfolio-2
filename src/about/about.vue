

<script setup lang="ts">
  
  
  import Description from './components/description.vue'
  import AboutHeader from './components/aboutHeader.vue'
  import AboutCard from './components/aboutCard.vue'
  
</script>

<template>
  <div class="flex flex-col justify-center w-full gap-2 ">
    <AboutHeader/>
    <div class="flex flex-col items-center justify-center w-full gap-4 rounded-sm">
      <Description class="w-full p-4"/>
      <AboutCard/>
    </div>
  </div>
</template>

<style scoped>


</style>

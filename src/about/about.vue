

<script setup lang="ts">
  
  
  import Description from './components/description.vue'
  import AboutHeader from './components/aboutHeader.vue'
  import AboutLinks from './components/aboutLinks.vue'
  import AboutSkillsAndHead from './components/aboutSkillsAndHead.vue'
  import AboutLanguageAndHobbies from './components/aboutLanguageAndHobbies.vue'
  import ThreeAudioVisual from './components/threeAudioVisual.vue';
</script>

<template>
  <div class="flex flex-col justify-center w-full gap-2 ">
    <AboutHeader/>
    <div class="flex flex-col justify-center w-full gap-4 rounded-sm">
      <Description class="w-full p-2"/>
      <AboutSkillsAndHead/>
    </div>
    <div class="flex items-center justify-between">
      <AboutLinks/>
      <AboutLanguageAndHobbies/>
    </div>

  </div>
</template>

<style scoped>


</style>

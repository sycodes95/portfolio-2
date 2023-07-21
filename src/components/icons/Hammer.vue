
<template>
  <svg-icon type="mdi" :path="path"></svg-icon>
</template>

<script lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiHammerScrewdriver } from '@mdi/js';

export default {
  name: "Hammer",
  components: {
    SvgIcon
  },
  data() {
    return {
       path: mdiHammerScrewdriver,
    }
  }
}
</script>
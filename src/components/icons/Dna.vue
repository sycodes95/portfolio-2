<script lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiDna } from '@mdi/js';

export default {
  name: "Dna",
  components: {
    SvgIcon
  },
  data() {
    return {
       path: mdiDna,
    }
  }
}
</script>

<template>
  <svg-icon type="mdi" :path="path"></svg-icon>
</template>
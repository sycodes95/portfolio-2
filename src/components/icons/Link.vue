<template>
  <svg-icon type="mdi" :path="path"></svg-icon>
</template>

<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiLinkVariant } from '@mdi/js';

const path = mdiLinkVariant;
</script>
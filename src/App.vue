<template>
  <RouterView class="rw" />
</template>

<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<style scoped lang="scss">
@font-face {
  font-family: 'Montserrat';
  src: url('~@/assets/fonts/Montserrat-Regular.ttf');
}
.rw {
  margin: 0px !important;
  padding: 0px !important;
}
//General
img {
  max-width: 100%;
  max-height: 100%;
}
</style>

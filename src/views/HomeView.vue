<template>
  <div class="home-container">
    <div class="settings">
      <v-btn
        variant="flat"
        color="transparent"
        icon="mdi-theme-light-dark"
        theme="light"
        @click="toggleTheme"
      ></v-btn>
    </div>
    <AppGreeting />
    <AppJobs />
    <AppProjects />
  </div>
</template>

<script setup lang="ts">
import { useTheme } from 'vuetify'
import AppGreeting from '@/components/AppGreeting.vue'
import AppJobs from '@/components/AppJobs.vue'
import AppProjects from '@/components/AppProjects.vue'
const theme = useTheme()

function toggleTheme() {
  if (theme.global.name.value === 'light') {
    theme.global.name.value = 'dark'
  } else if (theme.global.name.value === 'dark') {
    theme.global.name.value = 'light'
  }
}
</script>

<style scoped lang="scss">
.settings {
  position: absolute;
}

//Site
.home-container {
  //height: 100vh;
  width: 100vw;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  //overflow-y: scroll;
}
</style>

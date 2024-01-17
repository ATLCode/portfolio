<template>
  <div class="jobs">
    <div class="jCard" v-for="job in jobs" :key="job.title">
      <div class="jTimeline">{{ job.started }} - {{ job.finished }}</div>
      <div class="jContent">
        <div class="jTitle">{{ job.title }} • {{ job.company }}</div>
        <div class="jDescription">{{ job.description }}</div>
        <div class="jSkills"></div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const jobs = [
  {
    title: 'Software Developer',
    company: 'Onebyte Oy',
    started: '2022',
    finished: 'Present',
    description: 'Test description',
    tech: []
  },
  {
    title: 'Professional Coach',
    company: 'Basketball & Esports',
    started: '2015',
    finished: '2022',
    description: 'Test Description',
    tech: []
  }
]
</script>

<style scoped lang="scss">
.jobs {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid white;

  .jCard {
    width: fit-content;
    display: flex;
    gap: 1rem;
    padding: 1rem;
    .jTimeline {
    }
    .jContent {
    }
  }
}
</style>

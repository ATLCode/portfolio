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
    <div class="introduction">
      <div class="iName"></div>
      <div class="iDescription"></div>
      <div class="iLinks"></div>
    </div>
    <div class="jobs">
      <div class="jHeader">Experience</div>
      <div class="jCard"></div>
    </div>
    <div class="projects">
      <div class="pHeader">Projects</div>
      <div class="pCard" v-for="project in projects" :key="project.name">
        <div class="pImage">
          <v-img :width="400" aspect-ratio="16/9" cover :src="project.img"></v-img>
        </div>
        <div class="pInfo">
          <div class="pName">{{ project.name }}</div>
          <div class="pDescription">{{ project.description }}</div>
          <div class="pExtra"></div>
        </div>
        <div class="pTech">
          <div class="pTechLogo" v-for="icon in project.tech" :key="icon">
            <v-img
              :width="100"
              aspect-ratio="16/9"
              cover
              :src="`/src/assets/icons/${icon}.svg`"
            ></v-img>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useTheme } from 'vuetify'
const theme = useTheme()
const projects = [
  {
    name: 'test',
    description: 'asd',
    img: '/src/assets/images/test.jpg',
    tech: ['css', 'django'],
    github: ''
  },
  {
    name: 'test2',
    description: 'asd2',
    img: '/src/assets/images/test.jpg',
    tech: ['git', 'github'],
    github: ''
  },
  {
    name: 'test3',
    description: 'asd3',
    img: '/src/assets/images/test.jpg',
    tech: [],
    github: ''
  }
]

const jobs = [
  {
    title: 'Software Developer',
    company: 'Onebyte Oy',
    started: '2022',
    finished: 'present',
    description: '',
    tech: []
  },
  {
    title: 'Professional Coach',
    company: 'Basketball & Esports',
    started: '2012',
    finished: 'present',
    description: '',
    tech: []
  }
]

function toggleTheme() {
  if (theme.global.name.value === 'light') {
    theme.global.name.value = 'dark'
  } else if (theme.global.name.value === 'dark') {
    theme.global.name.value = 'light'
  }
}
</script>

<style scoped lang="scss">
//General
img {
  max-width: 100%;
  max-height: 100%;
}
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
.introduction {
  height: 100vh;
  //background-color: red;
}
.jobs {
  min-height: 100vh;
  background-color: blue;
  display: flex;
  flex-direction: column;
  .jHeader {
    background-color: yellow;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
.projects {
  min-height: 100vh;
  background-color: blue;
  display: flex;
  flex-direction: column;
  .pHeader {
    background-color: yellow;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .pCard {
    background-color: pink;
    height: 400px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1rem;
    .pImage {
      max-width: 100%;
      display: block;
      margin: auto;
      justify-content: center;
      align-items: center;
      background-position: center;
    }
    .pInfo {
      display: grid;
      grid-template-rows: 100px 300px;
      .pName {
        display: flex;
        justify-content: center;
        align-items: center;
      }
      .pDescription {
      }
    }
    .pTech {
      display: flex;
    }
  }
}
</style>

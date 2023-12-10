<template>
  <div class="home-container">
    <div class="introduction">test</div>
    <div class="projects">
      <div class="pHeader">Projects</div>
      <div class="pCard">
        <div class="pImage"></div>
        <div class="pInfo">
          <div class="pName">Project Name</div>
          <div class="pDescription">Project description</div>
        </div>
        <div class="pTech">Tech</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
//General
img {
  max-width: 100%;
  max-height: 100%;
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
  background-color: red;
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
      display: flex;
      justify-content: center;
      align-items: center;
      background-image: URL(../assets/images/test.jpg);
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
    }
  }
}
</style>

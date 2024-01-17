<template>
  <div class="introduction">
    <div id="iName" class="iName"></div>
    <div class="iDescription">
      <span>Software </span>
      <span>Developer</span>
    </div>
    <div class="iLinks">
      <a href="https://www.linkedin.com/in/aleksanteri-leinonen/" target="_blank">
        <font-awesome-icon class="icon i1" size="2xl" icon="fa-brands fa-linkedin" />
      </a>
      <a href="https://github.com/ATLCode" target="_blank">
        <font-awesome-icon class="icon i2" size="2xl" icon="fa-brands fa-github" />
      </a>
    </div>
  </div>
</template>

<script setup lang="ts">
import Vara from 'vara'
import { onMounted } from 'vue'

onMounted(() => {
  new Vara('#iName', 'https://cdn.jsdelivr.net/npm/vara@1.4.0/fonts/Satisfy/SatisfySL.json', [
    {
      text: 'Aleksanteri Leinonen', // String, text to be shown
      fontSize: 80, // Number, size of the text
      strokeWidth: 0.8, // Width / Thickness of the stroke
      color: 'white', // Color of the text
      id: '', // String or integer, for if animations are called manually or when using the get() method. Default is the index of the object.
      duration: 2000, // Number, Duration of the animation in milliseconds
      textAlign: 'center', // String, text align, accepted values are left,center,right
      autoAnimation: true, // Boolean, Whether to animate the text automatically
      queued: true, // Boolean, Whether the animation should be in a queue,
      delay: 0, // Number, Delay before the animation starts in milliseconds
      letterSpacing: 0 // Number, space between each character
    }
  ])
})
</script>

<style scoped lang="scss">
.introduction {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.iName {
  width: 100%;
  min-height: 100px;
}
.iDescription {
  transform: scale(0.94);
  animation: scale 3s forwards cubic-bezier(0.5, 1, 0.89, 1);
  font-family: 'Montserrat';
  font-size: 34px;
  span {
    opacity: 0;
    filter: blur(4px);
  }
  span:nth-child(1) {
    animation: fade-in 1s 1s forwards cubic-bezier(0.11, 0, 0.5, 0);
  }

  span:nth-child(2) {
    animation: fade-in 1s 1s forwards cubic-bezier(0.11, 0, 0.5, 0);
  }
  @keyframes scale {
    100% {
      transform: scale(1);
    }
  }
  @keyframes fade-in {
    100% {
      opacity: 1;
      filter: blur(0);
    }
  }
}

.iLinks {
  position: absolute;
  bottom: 20%;
  display: flex;
  flex-direction: row;
  width: 3rem;
  gap: 1rem;
  opacity: 0;
  animation: scale 3s forwards cubic-bezier(0.5, 1, 0.89, 1);
  animation: fadeIn 1s 2s forwards cubic-bezier(0.11, 0, 0.5, 0);

  @keyframes scale {
    100% {
      transform: scale(1);
    }
  }
  @keyframes fadeIn {
    100% {
      opacity: 1;
    }
  }

  a {
    .icon {
      color: white;
      border-radius: 50%;
      height: 50px;
      &:hover {
        //box-shadow: 0 0 10px 5px white;
        filter: drop-shadow(0 0 5px white);
      }
    }
  }
}
</style>

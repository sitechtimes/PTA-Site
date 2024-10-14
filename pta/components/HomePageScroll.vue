<template>
  <div class="container__ScrollDown">
    <img ref="arrow" src="/ScrollDown.svg" alt="scroll to top button" @click="scrollDown" />
  </div>
</template>

<script setup>
import gsap from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
const arrow = ref();

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  const tl = gsap.timeline();
  tl
    .from(arrow.value, { opacity: 0, delay: 1, duration: 1 })
    .from(arrow.value, { duration: 0.3, y: -10 }, "<")
    .to(arrow.value, { duration: 0.8, y: -30, repeat: -1, yoyo: true });
});

function scrollDown() {
  const element = document.getElementById("section__MiddleSection");
  element.scrollIntoView({ behavior: "smooth" });
}
</script>

<style scoped>
.test {
  margin-top: 50vw;
  overflow-x: hidden;
}
.container__ScrollDown {
  width: 100vw;
  display: flex;
  flex-direction: row;
  align-content: center;
  justify-content: center;
}

.container__ScrollDown img {
  width: 4rem;
  position: absolute;
  display: block;
  bottom: 1.5rem;
  margin: auto;
  opacity: 0.8;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  translate: (50%);
  -webkit-animation: scrolling 2s infinite;
  animation: scrolling 2s infinite;
  box-sizing: border-box;
  translate: (50);
}

@-webkit-keyframes scrolling {
  0% {
    -webkit-transform: rotate(-45deg) translate(0, 0);
    opacity: 0;
  }

  50% {
    opacity: 1;
  }

  100% {
    -webkit-transform: rotate(-45deg) translate(-20px, 20px);
    opacity: 0;
  }
}
@media only screen and (max-width: 1600px) {
  .container__ScrollDown img {
    bottom: 9rem;
  }
}
@media only screen and (max-width: 1500px) {
  .container__ScrollDown img {
    bottom: 2rem;
  }

  .test {
    margin-top: 50vw;
    overflow-x: hidden;
  }
}
@media only screen and (max-width: 1400px) {
  .container__ScrollDown img {
    bottom: 13rem;
  }
}
@media only screen and (max-width: 1200px) and (orientation: landscape) {
  .container__ScrollDown img {
    display: none;
  }
}
@media only screen and (max-width: 850px) and (orientation: landscape) {
  .container__ScrollDown img {
    display: none;
  }
}
@media only screen and (max-width: 850px) and (orientation: portrait) {
  .container__ScrollDown img {
    display: none;
  }
}
@media screen and (max-height: 1200px) and (orientation: portrait) {
  .container__ScrollDown img {
    display: none;
  }
}
</style>

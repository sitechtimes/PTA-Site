<template>
<div>
     <div id="gradient"></div>
<DonateTop />
        <div
          id="homePageScroll"
          ref="homePageScroll"
          :style="{ opacity: scrollOpacity }"
        >
          <DonateScroll />
        </div>
<DonateMid />
</div>
</template>
<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
import { onMounted, onUnmounted, ref } from "vue";

const homePageScrollRef = ref(null);
const scrollOpacity = ref(1);

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  // console.log("Scroll Position:", scrollPosition);

  if (scrollPosition >= 400) {
    scrollOpacity.value = 0;
  } else {
    scrollOpacity.value = 1;
  }
};

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
export default {
  mounted() {

  }

};
</script>
<style scoped>
@import url(../assets/base.css);
#gradient {
  width: 100%;
  height: 80vw;
  position: absolute;
  top: 0;
  left: 0;
  padding: 0;
  background: var(--bg-gradient);
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
  align-items: center;
  overflow-x: hidden;
  z-index: -1;
  overflow-x: hidden;
}


</style>
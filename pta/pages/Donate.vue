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
    <NewFooter />
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

export default {
  data() {
    return {
      scrollOpacity: 1,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition >= 400) {
        this.scrollOpacity = 0;
      } else {
        this.scrollOpacity = 1;
      }
    }
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
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
}

@media screen and (max-width: 576px) {
  #gradient {
    width: 100%;
    height: 220vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 576px) {
  #gradient {
    width: 100%;
    height: 100vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 576px) and (orientation: landscape) {
  #gradient {
    width: 100%;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 768px) {
  #gradient {
    width: 100%;
    height: 75vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
  #gradient {
    width: 100%;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}
</style>

<template>
  <div>
    <div class="parent">
      <div class="div1">
        <HomeTop />
        <div
          id="homePageScroll"
          ref="homePageScroll"
          :style="{ opacity: scrollOpacity }"
        >
          <HomePageScroll />
        </div>
      </div>
      <div class="div3">
        <AboutUs />
        <div class="div2">
          <MiddleSection />
        </div>
                            <Resources />
      </div>
    </div>
    <div id="footer">
      <NewFooter />
    </div>
  </div>
</template>

<script setup>
import { gsap } from "gsap/dist/gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

useHead({
  script: [
    { src: "https://identity.netlify.com/v1/netlify-identity-widget.js" },
  ],
});
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
</script>

<style scoped>
#homePageScroll {
  transition: opacity 0.3s ease;
}
.parent {
  display: flex;
  flex-direction: column;
}

.div1 {
  grid-area: 1 / 1 / 2 / 2;
  height: 40vw;
  width: 60%;
}

.div2 {
  display: flex;
  flex-direction: row;
  width: 100%;
}

@media screen and (max-width: 1400px) {
  .div1 {
  }
}
@media screen and (max-width: 1200px) {
  .div1 {
    height: 35vw;
  }
}
@media screen and (max-width: 992px) {
  .div1 {
  }
}
@media screen and (max-width: 768px) and (orientation: landscape) {
  .parent {
    margin-top: 5rem;
  }
}
@media only screen and (max-width: 576px) {
  .div1 {
    height: 125vw;
  }
}
@media only screen and (max-width: 576px) and (orientation: landscape) {
  .div1 {
    height: 140vh;
  }
}
@media only screen and (max-width: 450px) {
  .div1 {
    height: 135vw;
  }
}
@media only screen and (max-width: 356px) {
  .div1 {
    height: 150vw;
  }
}
</style>

<template>
  <div class="container__topArrow">
    <!-- <a href="#section__LandingSection"> -->
    <img src="/back-to-top-arrow.svg" @click="scroll" />
    <!-- </a> -->
  </div>
</template>

<script>
export default {
  methods: {
    scroll() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.container__topArrow {
  display: flex;
  height: 3rem;
  opacity: 0.7;
  position: fixed;
  bottom: 1.25rem;
  right: 1.8rem;
  scroll-behavior: smooth;
}

@media screen and (max-width: 1200px) {
  .container__topArrow {
    height: 3rem;
    bottom: 3rem;
    right: 1.8rem;
  }

  .container__topArrow img {
    height: 5rem;
  }
}

@media screen and (max-width: 992px) {
  .container__topArrow {
    height: 2rem;
    bottom: 5rem;
    right: 1.8rem;
  }
  .container__topArrow img {
    height: 5rem;
  }
}

@media screen and (max-width: 576px) {
  .container__topArrow {
    height: 1.5rem;
    bottom: 2.5rem;
    right: 1rem;
  }

  .container__topArrow img {
    height: 3rem;
  }
}
</style>

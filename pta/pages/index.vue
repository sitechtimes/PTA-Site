<template>
  <div>
    <div class="parent">
      <div class="div1">
        <HomeTop />
        <HomePageScroll />
      </div>
      <div class="div2">
        <MiddleSection />
      </div>
    </div>
  </div>
</template>

<script setup>
useHead({
  script: [
    { src: "https://identity.netlify.com/v1/netlify-identity-widget.js" },
  ],
});
</script>

<style scoped>
.parent {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(2, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
}

.div1 {
  grid-area: 1 / 1 / 2 / 2;
  height: 100vh;
  width: 60%;
}

.div2 {
  display: flex;
  flex-direction: row;
  width: 90%;
}
@media screen and (max-width: 768px) and (orientation: landscape) {
  .parent {
    margin-top: 5rem;
  }
}
@media only screen and (max-width: 576px) {
  .div1 {
    height: 145vh;
  }
}
@media only screen and (max-width: 356px) {
  .div1 {
    height: 0;
  }
}
</style>

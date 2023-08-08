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
    <div id="footer">
      <Footer />
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
#footer{
  margin-top: -20vw;
}
.parent {
  display: flex;
  flex-direction: column;
}

.div1 {
  grid-area: 1 / 1 / 2 / 2;
  height: 56vw;
  width: 60%;
}

.div2 {
  display: flex;
  flex-direction: row;
  width: 100%;
}
@media screen and (max-width: 1400px) {
  .div1 {
    height: 50vw;
  }
}
@media screen and (max-width: 1200px) {
  .div1 {
    height: 45vw;
  }
}
@media screen and (max-width: 992px) {
  .div1 {
    height: 50vw;
  }
}
@media screen and (max-width: 768px) and (orientation: landscape) {
  .parent {
    margin-top: 5rem;
  }
}
@media only screen and (max-width: 576px) {
  .div1 {
    height: 145vw;
  }
}
@media only screen and (max-width: 576px) and (orientation: landscape) {
  .div1 {
    height: 140vh;
  }
}
@media only screen and (max-width: 450px) {
  .div1 {
    height: 165vw;
  }
}
@media only screen and (max-width: 356px) {
  .div1 {
    height: 175vw;
  }
}
</style>

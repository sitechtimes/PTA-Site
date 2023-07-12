<script></script>
<template>
  <div>
    <Navbar />
    <div class="parent">
      <div class="div1">
        <HomeTop />
      </div>
      <div class="div2">
        <MiddleSection />
      </div>
      <ScrollTop/> 
      <Footer />
    </div>
  </div>
</template>
<style scoped>
.parent {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(2, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
}

.div1 {
  /* grid-area: 1 / 1 / 2 / 2; */
  height: 100vh;
  width: 50%;
}

.div2 {
  grid-area: 2 / 1 / 3 / 2;
  width: 50%;
}
</style>

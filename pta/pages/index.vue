<template>
  <div>
    <div class="parent">
      <div class="div1">
        <HomeTop />
      </div>
      <div class="div2">
        <MiddleSection />
      </div>
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
  grid-area: 1 / 1 / 2 / 2;
  height: 100vh;
  width: 60%;
}

.div2 {
display: flex;
flex-direction: row;
  width: 90%;
}
</style>
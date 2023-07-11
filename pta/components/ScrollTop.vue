<template>
  <div class="container__topArrow">
    <a href="#homeTopCon" class="anchor__topArrow">
      <img src="/back-to-top-arrow.svg" >
    </a>
  </div>
</template>

<style scoped>
.container__topArrow {
  height: 3rem;
  opacity: 0.7;
  position: fixed;
  bottom: 5%;
  right: 5%;
  scroll-behavior: smooth;
}/* 
@media screen and (max-width: 1200px){
.container__topArrow {
  height: 3rem;
  right: 2%;
    bottom: 5%;
}
}
@media screen and (max-width: 992px){
.container__topArrow {
  height: 2rem;
  right: 3%;
  bottom: 4%;
}
}
@media screen and (max-width: 576px) {
  .container__topArrow {
    height: 1.5rem;
bottom: 3%;
right: 2%;
  }

} */
</style>

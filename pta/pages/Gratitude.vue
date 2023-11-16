<template>
<div>
       <div id="gradient"></div>
       <Wall />

</div>
</template>

<style scoped>
@import url(../assets/base.css);

#gradient {
  width: 100%;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  height: 80rem;
  z-index: -5;
  background: linear-gradient(
    180deg,
    #feb89a 0%,
    #fdd8b8 18%,
    #ffecc5 40%,
    #faf2e1 75%,
    #faf2e1 80%,
    #fff 95%
  );
  overflow-x: hidden;
}
</style>
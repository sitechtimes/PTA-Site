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
  background: var(--bg-gradient);
  overflow-x: hidden;
}
</style>

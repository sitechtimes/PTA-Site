<template>
<div>
     <div id="gradient"></div>
<DonateTop />
<DonateMid />
</div>
</template>
<script>
import { gsap } from "gsap";
export default {
  mounted() {
    gsap.from(".heading", { duration: 1, y: 100, opacity: 0 });
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
  overflow-x: hidden;
}


</style>
<template>
<div>
     <div id="gradient"></div>
                <h1 class="heading">DONATIONS</h1>
                <h3 class="subh" ref="subh">Bake Sales</h3>
                <p ref="text">Food and drink donations would be much appreciated to help launch bake sales during the year. Our students always enjoy these added treats to their daily lunch routine. </p>
                <p ref="text2">Attached is a wish list of items that we would like to provide to our students which include (NO NUTS) :</p>
</div>
</template>
<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { subh } = this.$refs;
    const { text } = this.$refs;
        const { text2 } = this.$refs;
    gsap.from(".heading", { duration: 1, y: 100, opacity: 0 });
    gsap.from(subh, { delay: 0.5, duration: 1, y: 100, opacity: 0 });
    gsap.from(text, { delay: 0.8, duration: 1, y: 100, opacity: 0 });
        gsap.from(text2, { delay: 1, duration: 1, y: 100, opacity: 0 });
  },
};
</script>
<style scoped>
@import url(../assets/base.css);
p {
  font-size: 1.5vw;
margin: 1% 0 0 8%;
width: 67%;
font-family: var(  --font-text);
}
.heading{
margin: 2% 0 0 8%;
}
.subh {
  margin-top: 1.5rem;
  width: 32vw;
margin: 2% 0 0 8%;
    margin-top: 1.5rem;
}
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
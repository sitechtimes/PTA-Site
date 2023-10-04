<template>
<div>
        <div id="gradient" >
            <h1 class="heading" ref="heading">Wall of Gratitude</h1>
    </div>
</div>
   
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { heading } = this.$refs;
    gsap.from(heading, { delay: 0, duration: 1, y: 100, opacity: 0 })


  }

};
</script>
<style>

#gradient {
  width: 100%;
  height: 90vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background:linear-gradient(
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

.heading {
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  font-size: 4rem;
  color: #483221;
  margin: 10% 0 0 8%;
}
</style>
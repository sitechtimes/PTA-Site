<template>
  <div>
    <div id="gradient">
      <div class="topComponent">
        <div class="leftComponent">
          <h1 class="heading" ref="heading">Wall of Gratitude</h1>
          <div class="thanks">
            <h2>Thank You!</h2>
            <p>
              We would like to thank everyone who helped out Lorem ipsum dolor
              sit amet, consectetur adipiscing elit, sed do eiusmod tempor
              incididunt ut labore et dolore magna aliqua. Ut enim ad minim
              veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
              ex ea commodo consequat. Ut enim ad minim veniam, quis nostrud
              exercitation ullamco laboris nisi ut aliquip ex ea commodo
              consequat. Ut enim ad minim veniam, quis nostrud exercitation
              ullamco laboris nis
            </p>
          </div>
        </div>
        <div class="image"></div>
        <div class="archive"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { heading } = this.$refs;
    gsap.from(heading, { delay: 0, duration: 1, y: 100, opacity: 0 });
  },
};
</script>
<style scoped>
#gradient {
  width: 100%;
  height: 150vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
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
.topComponent {
  display: flex;
  flex-direction: row;
}
.heading {
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  font-size: 6rem;
  color: #483221;
  margin: 10% 0 0 8%;
  width: 33rem;
  background-color: red;
}
.thanks {
  font-family: "Kumbh Sans", san serif;
  font-weight: 400;
  font-size: 1.6rem;
  color: #483221;
  margin: 2% 0 0 8%;
  width: 40rem;
  background-color: red;
}
.image {
  width: 500px;
  height: 500px;
  border-radius: 50%;
  background-color: red;
}
</style>

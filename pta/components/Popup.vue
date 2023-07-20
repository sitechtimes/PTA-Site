<template>
  <div id="popupscreen">
    <div id="outside" @click="TogglePopup()"></div>
    <div class="popup" ref="popup">
      <div class="popup-inner">
        <button class="popup-close" @click="TogglePopup()">✖</button>
        <slot />
      </div>
    </div>
  </div>
</template>
<script>
import { gsap } from "gsap";
export default {
  props: ["TogglePopup"],
  mounted() {
    let tl = gsap.timeline();
    tl.from(".popup", { scale: 0.3, duration: 0.4 });
  },
};
</script>
<style scoped>
#outside {
  background: transparent;
  height: 100vh;
  width: 100vw;
}
.popup-close {
  border: none;
  font-weight: bold;
  right: 4vw;
  background: transparent;
  position: fixed;
  top: 10%;
  font-size: 2.2vw;
  cursor: pointer;
}
#popupscreen {
  width: 100vw;
  height: auto;
  background-color: #0000003f;
  position: fixed;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  z-index: 99;
}
.popup {
  background: white;
  position: absolute;
  top: 50%;
  left: 50%;
  padding: 3rem;
  transform: translate(-50%, -50%);
  color: var(--text-color);
  font-family: var(--font-text);
  border-radius: 2vw;
  font-size: 1vw;
  width: 40vw;
}
button {
  transition: 0.3s;
}
button:hover {
  opacity: 0.7;
}

/* media queries max width
    sm:  ≥576px
  md:  ≥768px
    lg:  ≥992px
    xl:  ≥1200px
    xxl: ≥1400px
    */
@media only screen and (max-width: 1200px) {
  .popup-close {
    top: 12%;
    font-size: 3vw;
  }
}
@media only screen and (max-width: 992px) {
  .popup-close {
    top: 13%;
    font-size: 3.4vw;
  }
  .popup {
    width: 50vw;
  }
}
@media only screen and (max-width: 768px) {
  .popup-close {
    font-size: 4.5vw;
  }
}
@media only screen and (max-width: 576px) {
  .popup-close {
    font-size: 4vw;
  }
  .popup {
    width: 60vw;
    padding: 2rem;
  }
}
@media only screen and (max-width: 356px) {
  .popup-close {
    font-size: 5vw;
    top: 12%;
  }
}
</style>

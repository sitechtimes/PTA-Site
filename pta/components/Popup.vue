<template>
  <div id="popupscreen">
    <div id="outside" @click="TogglePopup()"></div>
    <div class="popup">
      <div class="popup-inner">
        <button class="popup-close" @click="TogglePopup()">✖</button>
        <slot />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["TogglePopup"],
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
  right: 3vw;
  background: transparent;
  position: fixed;
  top: 10%;
  font-size: 2.5vw;
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
  transform: translate(-50%, -50%);
  color: var(--text-color);
  font-family: var(--font-text);
  padding: 2rem;
  border-radius: 2vw;
  font-size: 1vw;
  width: 40vw;
}

/* media queries max width
    sm:  ≥576px
  md:  ≥768px
    lg:  ≥992px
    xl:  ≥1200px
    xxl: ≥1400px
    */

@media screen and (max-width: 576px) {
  .popup-close {
    font-size: 4vw;
  }
  .popup {
    width: 15rem;
  }
}
</style>

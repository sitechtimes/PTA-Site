<template>
  <div class="menu">
    <input v-model="checked" @click="toggle" type="checkbox" id="active" />
    <label for="active" class="menu-btn"><span></span></label>
    <label for="active" class="close"></label>
    <Transition name="slide">
      <div v-if="show" class="wrapper">
        <ul class="link-container">
          <li class="link" @click="toggle">
            <img
              id="home"
              src="../components/icons/NavBar-Icons/house.svg"
              alt="brown icon of house"
            />
            <router-link class="menu-router" to="/"> Home </router-link>
          </li>
          <li class="link" @click="toggle">
            <img
              id="events"
              src="../components//icons/NavBar-Icons/calendar.svg"
              alt="brown icon of calendar"
            />
            <router-link class="menu-router" to="/Events"> Events </router-link>
          </li>
          <li class="link" @click="toggle">
            <img
              id="contact"
              src="../components//icons/NavBar-Icons/envelope.svg"
              alt="brown icon of envelope"
            />
            <router-link class="menu-router" to="/ContactUs">
              Contact
            </router-link>
          </li>
          <li class="link" @click="toggle">
            <img
              id="donate"
              src="../components//icons/NavBar-Icons/credit_card.svg"
              alt="brown icon of credit card"
            />
            <router-link class="menu-router" to="/Donate"> Donate </router-link>
          </li>
        </ul>
      </div></Transition
    >
  </div>
</template>
<script>
export default {
  name: "Menu",
  data() {
    return {
      checked: false,
      show: false,
    };
  },
  methods: {
    toggle() {
      this.show = !this.show;
      this.checked = !this.checked;
    },
  },
};
</script>
<style scoped>
@import url(../assets/base.css);
.slide-enter-active {
  animation: slide-right 0.3s;
}

img {
  width: 2rem;
}

.menu-router {
  font-size: 2rem;
}

.menu-btn {
  position: fixed;
}
@keyframes slide-right {
  0% {
    right: -100%;
  }
  50% {
    right: -100%;
  }
  100% {
    right: 0;
  }
}

.link-container {
  padding: 0;
  left: 0;
  padding-top: 2rem;
  padding-left: 1rem;
}
</style>

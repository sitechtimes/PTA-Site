<template>
  <div id="navbar">
    <div id="logoContainer">
      <NuxtLink to="/">
        <img
          class="logo"
          src="../components/icons/NavBar-Icons/pta-logo.png"
          alt=""
        />
      </NuxtLink>
    </div>
    <div id="naV">
      <div class="group">
        <NuxtLink to="/">
          <img
            class="icon"
            id="home"
            src="../components/icons/NavBar-Icons/house.svg"
            alt="dark brown icon of a house"
          />
          Home</NuxtLink
        >
      </div>
      <div class="group">
        <NuxtLink to="/Events">
          <img
            class="icon"
            id="events"
            src="../components/icons/NavBar-Icons/calendar.svg"
            alt="dark brown icon of a calendar"
          />
          Events</NuxtLink
        >
      </div>
      <div class="group">
        <NuxtLink to="/ContactUs">
          <img
            class="icon"
            id="contact"
            src="../components/icons/NavBar-Icons/envelope.svg"
            alt="dark brown icon of an envelope"
          />
          Contact</NuxtLink
        >
      </div>
      <div class="group">
        <NuxtLink to="/Donate">
          <img
            class="icon"
            id="donate"
            src="../components/icons/NavBar-Icons/credit_card.svg"
            alt="dark brown icon of a credit card"
          />
          Donate</NuxtLink
        >
      </div>
    </div>
    <Menu />
  </div>
</template>
<!-- <script>
import Menu from "./Menu.vue";
export default {
  components: { Menu },
  name: "Navbar",
  methods: {},
};
</script> -->
<style scoped>
@import url(../assets/base.css);
a:after{
  display: block;
  content: '';
  text-decoration: underline 3px var(--text-color);
  border-bottom: solid 3px var(--text-color);
  transform: scaleX(0);
  transition: transform 0.3s ease-in-out;
}
a:hover:after {
  transform: scaleX(1);
}

a.nuxt-link-exact-active {
  color: var(--text-color);
}
#naV {
  flex-direction: row;
  justify-content: center;
}

a {
  display: flex;
  width: 7rem;
  text-decoration: none;
  color: var(--text-color);
}

.logo {
  width: 10rem;
  position: absolute;
  left: 6.5%;
  top: 19.5%;
}

.icon {
  height: 30px;
  padding: 0 10px 0 0;
  margin-top: 1px;
}
#contact,
#donate {
  margin-top: 2px;
}

.group {
  width: 12rem;
  align-self: center;
  margin-top: 1.5rem;
}

a:visited {
  color: var(--text-color);
}

@media screen and (max-width: 1400px) {
  .group {
    width: 10rem;
  }
}

@media screen and (max-width: 1200px) {
  .icon {
    height: 1.8rem;
  }
  .group {
    margin-top: 1rem;
    /* font-size: 1.2rem;
    width: 9rem; */
  }
  .icon {
    margin-top: 3px;
  }
  #contact,
  #donate {
    margin-top: 5px;
  }
}
@media screen and (max-width: 992px) {
  .logo {
    width: 16vw;
  }
}
@media only screen and (max-width: 768px) {
  .logo {
    width: 8rem;
  }
}
@media only screen and (max-width: 576px) {
  .logo {
    width: 7.5rem;
  }
}
</style>

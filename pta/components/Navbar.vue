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
    <div id="nav">
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

#nav {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-shrink: 0;
}

a {
  display: flex;
  width: 10.5rem;
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
  margin-top: 4px;
}

#contact {
  padding-bottom: 0.1rem;
}

#donate {
  padding-bottom: 0.1rem;
}

.group {
  display: flex;
  width: 12rem;
  align-self: center;
}

a:visited {
  color: var(--text-color);
}

@media screen and (max-width: 1400px) {
  .group {
    width: 10rem;
  }
  .icon {
    height: 30px;
    padding: 0 10px 0 0;
    margin-top: -10px;
  }
}

@media screen and (max-width: 1200px) {
  .logo {
    width: 7rem;
  }

  .icon {
    width: 1.5rem;
  }

  .group {
    font-size: 1.2rem;
    width: 9rem;
  }
}

@media screen and (min-width: 992px) and (orientation: portrait) {
  .logo {
    width: 20vw;
    margin-top: 2vw;
  }
}
@media screen and (max-width: 768px) {
  .logo {
    width: 8rem;
  }
}

@media screen and (max-width: 576px) {
  #logo {
    width: 1rem;
  }
}
</style>

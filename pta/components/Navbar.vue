<template>
  <div id="navbar">
    <NuxtLink to="/" id="logoContainer">
      <img
        class="logo"
        src="../components/icons/NavBar-Icons/pta-logo.png"
        alt=""
      />
    </NuxtLink>
    <div id="nav">
      <div class="group">
        <img
          class="icon"
          id="home"
          src="../components/icons/NavBar-Icons/house.svg"
          alt="dark brown icon of a house"
        />
        <NuxtLink to="/">Home</NuxtLink>
      </div>
      <div class="group">
        <img
          class="icon"
          id="events"
          src="../components/icons/NavBar-Icons/calendar.svg"
          alt="dark brown icon of a calendar"
        />
        <NuxtLink to="/Events">Events</NuxtLink>
      </div>
      <div class="group">
        <img
          class="icon"
          id="contact"
          src="../components/icons/NavBar-Icons/envelope.svg"
          alt="dark brown icon of an envelope"
        />
        <NuxtLink to="/ContactUs">Contact</NuxtLink>
      </div>
      <div class="group">
        <img
          class="icon"
          id="donate"
          src="../components/icons/NavBar-Icons/credit_card.svg"
          alt="dark brown icon of a credit card"
        />
        <NuxtLink to="/Donate">Donate</NuxtLink>
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
  padding-right: 0.6rem;
  padding-bottom: 0.5rem;
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

@media screen and (max-width: 992px) {
}

@media screen and (max-width: 768px) {
}
@media screen and (max-width: 576px) {
  #logo {
    width: 1rem;
  }
}
</style>

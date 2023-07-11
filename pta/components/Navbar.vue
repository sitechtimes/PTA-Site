<template>
  <div id="navbar">
    <div id="logoContainer">
      <img
        class="logo"
        src="../components/icons/NavBar-Icons/pta-logo.png"
        alt=""
      />
    </div>
    <div id="nav">
      <div class="group" id="home">
        <img
          class="icon"
          src="../components/icons/NavBar-Icons/house.svg"
          alt="dark brown icon of a house"
        />
        <NuxtLink to="/">Home</NuxtLink>
      </div>
      <div class="group" id="events">
        <img
          class="icon"
          src="../components/icons/NavBar-Icons/calendar.svg"
          alt="dark brown icon of a calendar"
        />
        <NuxtLink to="/Events">Events</NuxtLink>
      </div>
      <div class="group" id="contact">
        <img
          class="icon"
          src="../components/icons/NavBar-Icons/envelope.svg"
          alt="dark brown icon of an envelope"
        />
        <NuxtLink to="/ContactUs">Contact Us</NuxtLink>
      </div>
      <div class="group" id="donate">
        <img
          class="icon"
          src="../components/icons/NavBar-Icons/credit_card.svg"
          alt="dark brown icon of a credit card"
        />
        <NuxtLink to="/Donate">Donate</NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);

#nav {
  display: flex;
  width: 63.5rem;
  justify-content: flex-end;
  flex-shrink: 0;
}

a {
  display: flex;
  width: 10.5rem;
  text-decoration: none;
}

#logo {
  justify-content: flex-start;
}

.icon {
  padding-right: 0.6rem;
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
  /*no change needed */
}

@media screen and (max-width: 1200px) {
  /*no change needed */
}

@media screen and (max-width: 992px) {
  #nav {
    width: 45rem;
  }

  a {
    width: 7rem;
  }

  .group {
    width: 10rem;
  }
}

@media screen and (max-width: 768px) {
  #nav {
    width: 25rem;
    font-size: 1.3rem;
  }

  a {
    width: 6.5rem;
  }

  .icon {
    max-width: 1.5rem;
  }

  .logo {
    max-width: 9rem;
    height: auto;
  }
}

@media screen and (max-width: 576px) {
  #nav {
    width: 27rem;
    font-size: 0.9rem;
  }

  a {
    width: 4rem;
  }

  .group {
    width: 6.5rem;
  }

  .icon {
    max-width: 1.2rem;
    padding-right: 0.3rem;
  }

  .logo {
    max-width: 8rem;
    height: auto;
  }
}
</style>

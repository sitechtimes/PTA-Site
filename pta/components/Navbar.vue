<template>
  <div id="navbar">
    <div id="logoContainer">
      <NuxtLink to="/" @click="this.page = home">
        <img
          class="logo"
          src="../components/icons/NavBar-Icons/pta-logo.png"
          alt=""
        />
      </NuxtLink>
    </div>
    <div id="naV">
      <div class="group">
        <NuxtLink
          to="/"
          id="homeLink"
          ref="homeLink"
          @click="(this.page = home), underline()"
        >
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
        <NuxtLink
          to="/Events"
          id="eventsLink"
          @click="(this.page = events), underline()"
        >
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
        <NuxtLink
          to="/ContactUs"
          id="contactLink"
          @click="(this.page = contact), underline()"
        >
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
        <NuxtLink
          to="/Donate"
          id="donateLink"
          @click="(this.page = donate), underline()"
        >
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

<script>
export default {
  data(){
    return {
      page: home,
    },
  },
  name: "Navbar",
  methods: {
    underline() {
      const { homeLink } = this.$refs;
      const { eventsLink } = this.$refs;
      const { contactLink } = this.$refs;
      const { donateLink } = this.$refs;
      if (this.page === home) {
        console.log(this.page)
        homeLink.style.text-decoration = "underline var(--text-color) 0.2rem"
        eventsLink.style.text-decoration = "none"
        contactLink.style.text-decoration = "none"
        donateLink.style.text-decoration = "none"
      } else if( this.page === events) {
        console.log(this.page)
        homeLink.style.text-decoration = "none"
        eventsLink.style.text-decoration = "underline var(--text-color) 0.2rem"
        contactLink.style.text-decoration = "none"
        donateLink.style.text-decoration = "none"
      } else if( this.page === contact) {
        console.log(this.page)
        homeLink.style.text-decoration = "none"
        eventsLink.style.text-decoration = "none"
        contactLink.style.text-decoration = "underline var(--text-color) 0.2rem"
        donateLink.style.text-decoration = "none"
      } else if( this.page === donate) {
        console.log(this.page)
        homeLink.style.text-decoration = "none"
        eventsLink.style.text-decoration = "none"
        contactLink.style.text-decoration = "none"
        donateLink.style.text-decoration = "underline var(--text-color) 0.2rem"
      },
    },
  },
};
</script>

<style scoped>
@import url(../assets/base.css);

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

a:hover {
  text-decoration: underline var(--text-color) 0.2rem;
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

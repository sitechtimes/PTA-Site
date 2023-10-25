<template>
  <div id="navbar">
    <div id="logoContainer">
      <NuxtLink to="/" @click="(page = 'index'), underline()">
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
          @click="(page = 'index'), underline()"
          v-bind:style="({ animation: fadeIn }, { textDecoration: homeLine })"
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
          ref="eventsLink"
          @click="(page = 'Events'), underline()"
          v-bind:style="({ animation: fadeIn }, { textDecoration: eventsLine })"
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
          ref="contactLink"
          @click="(page = 'ContactUs'), underline()"
          v-bind:style="
            ({ animation: fadeIn }, { textDecoration: contactLine })
          "
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
          to="/Gratitude"
          id="gratitudeLink"
          ref="gratitudeLink"
          @click="(page = 'Gratitude'), underline()"
          v-bind:style="
            ({ animation: fadeIn }, { textDecoration: gratitudeLine })
          "
        >
          <img
            class="icon"
            id="gratitude"
            src="../components/icons/NavBar-Icons/heart.svg"
            alt="dark brown icon of an envelope"
          />
          Gratitude</NuxtLink
        >
      </div>
      <div class="group">
        <NuxtLink
          to="/Donate"
          id="donateLink"
          ref="donateLink"
          @click="(page = 'Donate'), underline()"
          v-bind:style="({ animation: fade }, { textDecoration: donateLine })"
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
import { useRouter } from "vue-router";
export default {
  name: "Navbar",
  data() {
    return {
      page: String,
      homeLine: "underline var(--text-color) 0.2rem",
      eventsLine: "transparent",
      contactLine: "transparent",
      donateLine: "transparent",
      gratitudeLine: "transparent",
      fade: "fadeIn 5s;",
    };
  },
  methods: {
    underline() {
      if (this.page === "index") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "underline var(--text-color) 0.2rem";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "Events") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "transparent";
        this.eventsLine = "underline var(--text-color) 0.2rem";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "ContactUs") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "transparent";
        this.eventsLine = "transparent";
        this.contactLine = "underline var(--text-color) 0.2rem";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } 
      else if (this.page === "Gratitude") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "transparent";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "underline var(--text-color) 0.2rem";
        this.donateLine = "transparent";
      } 
      else if (this.page === "Donate") {
        console.log(this.page);
        this.fade = "fadeIn 10s;";
        this.homeLine = "transparent";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "underline var(--text-color) 0.2rem";
      }
    },
    currentRoute() {
      const router = useRouter();
      let currentPathObject = router.currentRoute.value;
      console.log(currentPathObject.name);
      this.page = currentPathObject.name;
      this.underline();
    },
  },
  mounted() {
    this.currentRoute();
  },
};
</script>

<style scoped>
@import url(../assets/base.css);

a {
  display: flex;
  width: 7rem;
  color: var(--text-color);
  transition: 0.3s;
}
a:hover{
  opacity: 0.7;
}
/* 
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
}*/
#naV {
  flex-direction: row;
  justify-content: center;
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

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-moz-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-webkit-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-o-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-ms-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
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

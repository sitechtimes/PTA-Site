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
      <div class="group">
        <svg id="translate" class="icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path d="M0 128C0 92.7 28.7 64 64 64H256h48 16H576c35.3 0 64 28.7 64 64V384c0 35.3-28.7 64-64 64H320 304 256 64c-35.3 0-64-28.7-64-64V128zm320 0V384H576V128H320zM178.3 175.9c-3.2-7.2-10.4-11.9-18.3-11.9s-15.1 4.7-18.3 11.9l-64 144c-4.5 10.1 .1 21.9 10.2 26.4s21.9-.1 26.4-10.2l8.9-20.1h73.6l8.9 20.1c4.5 10.1 16.3 14.6 26.4 10.2s14.6-16.3 10.2-26.4l-64-144zM160 233.2L179 276H141l19-42.8zM448 164c11 0 20 9 20 20v4h44 16c11 0 20 9 20 20s-9 20-20 20h-2l-1.6 4.5c-8.9 24.4-22.4 46.6-39.6 65.4c.9 .6 1.8 1.1 2.7 1.6l18.9 11.3c9.5 5.7 12.5 18 6.9 27.4s-18 12.5-27.4 6.9l-18.9-11.3c-4.5-2.7-8.8-5.5-13.1-8.5c-10.6 7.5-21.9 14-34 19.4l-3.6 1.6c-10.1 4.5-21.9-.1-26.4-10.2s.1-21.9 10.2-26.4l3.6-1.6c6.4-2.9 12.6-6.1 18.5-9.8l-12.2-12.2c-7.8-7.8-7.8-20.5 0-28.3s20.5-7.8 28.3 0l14.6 14.6 .5 .5c12.4-13.1 22.5-28.3 29.8-45H448 376c-11 0-20-9-20-20s9-20 20-20h52v-4c0-11 9-20 20-20z"/></svg>
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
#translate{
  margin-top: 10px;
  fill: var(--text-color);
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

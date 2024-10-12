<template>
  <div id="navbar">
    <div id="logoContainer">
      <NuxtLink to="/" @click="(page = 'index'), underline()">
        <img
          class="logo"
          src="../components/icons/NavBar-Icons/pta-logo.png"
          alt="PTA Logo"
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
          v-bind:style="{ animation: fade, textDecoration: homeLine }"
        >
          <img
            class="icon"
            id="home"
            src="../components/icons/NavBar-Icons/house.svg"
            alt="dark brown icon of a house"
          />
          Home
        </NuxtLink>
      </div>
      <div class="group">
        <NuxtLink
          to="/Events"
          id="eventsLink"
          ref="eventsLink"
          @click="(page = 'Events'), underline()"
          v-bind:style="{ animation: fade, textDecoration: eventsLine }"
        >
          <img
            class="icon"
            id="events"
            src="../components/icons/NavBar-Icons/calendar.svg"
            alt="dark brown icon of a calendar"
          />
          Events
        </NuxtLink>
      </div>
      <div class="group">
        <NuxtLink
          to="/ContactUs"
          id="contactLink"
          ref="contactLink"
          @click="(page = 'ContactUs'), underline()"
          v-bind:style="{ animation: fade, textDecoration: contactLine }"
        >
          <img
            class="icon"
            id="contact"
            src="../components/icons/NavBar-Icons/envelope.svg"
            alt="dark brown icon of an envelope"
          />
          Join Us
        </NuxtLink>
      </div>
      <div class="group">
        <NuxtLink
          to="/Donate"
          id="donateLink"
          ref="donateLink"
          @click="(page = 'Donate'), underline()"
          v-bind:style="{ animation: fade, textDecoration: donateLine }"
        >
          <img
            class="icon"
            id="donate"
            src="../components/icons/NavBar-Icons/credit_card.svg"
            alt="dark brown icon of a credit card"
          />
          Donate
        </NuxtLink>
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
      page: "",
      homeLine: "underline var(--text-color) 0.2rem",
      eventsLine: "transparent",
      contactLine: "transparent",
      donateLine: "transparent",
      gratitudeLine: "transparent",
      fade: "fadeIn 5s", 
    };
  },
  methods: {
    underline() {
      if (this.page === "index") {
        this.fade = "fadeIn 5s"; 
        this.homeLine = "underline var(--text-color) 0.2rem";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "Events") {
        this.fade = "fadeIn 5s";
        this.homeLine = "transparent";
        this.eventsLine = "underline var(--text-color) 0.2rem";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "ContactUs") {
        this.fade = "fadeIn 5s";
        this.homeLine = "transparent";
        this.eventsLine = "transparent";
        this.contactLine = "underline var(--text-color) 0.2rem";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "Gratitude") {
        this.fade = "fadeIn 5s"; 
        this.homeLine = "transparent";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "underline var(--text-color) 0.2rem";
        this.donateLine = "transparent";
      } else if (this.page === "Donate") {
        this.fade = "fadeIn 10s"; 
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
      this.page = currentPathObject.name || "index";
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
a:hover {
  opacity: 0.7;
}

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

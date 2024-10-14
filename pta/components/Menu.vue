<template>
  <div class="menu">
    <input v-model="checked" @click="toggle" type="checkbox" id="active" />
    <label for="active" class="menu-btn"><span></span></label>
    <label for="active" class="close"></label>
    <Transition name="slide">
      <div v-if="show" class="wrapper">
        <ul class="link-container">
          <p class="link" @click="toggle">
            <img id="home" src="../components/icons/NavBar-Icons/house.svg" alt="brown icon of house" />
            <router-link class="menu-router" to="/"> Home </router-link>
          </p>
          <p class="link" @click="toggle">
            <img id="events" src="../components//icons/NavBar-Icons/calendar.svg" alt="brown icon of calendar" />
            <router-link class="menu-router" to="/Events"> Events </router-link>
          </p>
          <p class="link" @click="toggle">
            <img id="contact" src="../components//icons/NavBar-Icons/envelope.svg" alt="brown icon of envelope" />
            <router-link class="menu-router" to="/ContactUs"> Join Us </router-link>
          </p>
          <p class="link" @click="toggle">
            <img id="donate" src="../components//icons/NavBar-Icons/credit_card.svg" alt="brown icon of credit card" />
            <router-link class="menu-router" to="/Donate"> Donate </router-link>
          </p>
        </ul>
      </div></Transition
    >
  </div>
</template>

<script setup>
const checked = ref(false);
const show = ref(false);

function toggle() {
  show.value = !show.value;
  checked.value = !checked.value;
}
</script>

<style scoped>
@import url(../assets/base.css);

.link-container {
  display: flex;
  flex-direction: column;
  margin-left: 8vw;
  margin-top: 12vw;
}
.link {
  display: inline-flex;
  flex-direction: row;
  margin: 1rem;
  list-style: none;
  height: 4vw;
}
a.menu-router {
  font-size: 2rem;
}
img {
  width: 2.8rem;
  height: 2.5rem;
  padding-top: 0.2rem;
  margin-right: 0.8rem;
}
#home,
#events {
  padding-top: 0.1rem;
}
.menu-btn {
  position: fixed;
}
.slide-enter-active {
  animation: slide-right 0.3s;
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
}
@media only screen and (max-width: 768px) and (orientation: landscape) {
}
@media only screen and (max-width: 768px) {
  .link-container {
    margin-left: 8vw;
    margin-top: 6vw;
  }
  .link {
    display: inline-flex;
    flex-direction: row;
    margin: 1.3rem;
    list-style: none;
    height: 3.3vw;
  }
  a.menu-router {
    font-size: 2rem;
  }
  img {
    width: 2rem;
    height: 2rem;
    padding-top: 0.8rem;
    margin-right: 1rem;
  }
  #home,
  #events {
    padding-top: 0.7rem;
  }
}
@media only screen and (max-width: 576px) {
  #home,
  #events {
    padding-top: 0.25rem;
  }
  .link-container {
    margin-top: 20vw;
  }

  .link {
    display: inline-flex;
    flex-direction: row;
    margin: 1.5rem;
    list-style: none;
    height: 3vw;
  }
  a.menu-router {
    font-size: 1.5rem;
  }
  img {
    width: 2rem;
    height: 1.8rem;
    padding-top: 0.4rem;
    margin-right: 0.5rem;
  }
}
@media only screen and (max-width: 356px) {
  .link-container {
    margin-top: 27vw;
  }
  .link {
    height: 11vw;
  }
}
</style>

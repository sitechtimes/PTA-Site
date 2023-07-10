<template>
  <div id="navbar">
    <div class="link" id="home">
      <img
        src="../assets/NavBar-Icons/house.svg"
        alt="dark brown icon of a house"
      />
      <NuxtLink to="/">Home</NuxtLink>
    </div>
    <div class="link" id="events">
      <img
        src="../assets/NavBar-Icons/calendar.svg"
        alt="dark brown icon of a calendar"
      />
      <NuxtLink to="/Events">Events</NuxtLink>
    </div>
    <div class="link" id="contact">
      <img
        src="../assets/NavBar-Icons/envelope.svg"
        alt="dark brown icon of an envelope"
      />
      <NuxtLink to="/ContactUs">Contact Us</NuxtLink>
    </div>
    <div class="link" id="donate">
      <img
        src="../assets/NavBar-Icons/credit_card.svg"
        alt="dark brown icon of a credit card"
      />
      <NuxtLink to="/Donate">Donate</NuxtLink>
    </div>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);

#navbar {
  display: flex;
  flex-shrink: 0;
  justify-content: flex-end;
  color: var(--text-color);
  font-family: var(--font-nav);
  font-size: 32px;
  font-weight: 400;
  letter-spacing: 0.64px;
  background: no-repeat url(../assets/NavBar-Icons/pta-logo.png);
}

a {
  display: flex;
  width: 163.834px;
  height: 40.966px;
  padding-top: 30px;
  padding-bottom: 35px;
  flex-direction: column;
  flex-shrink: 0;
  text-decoration: none;
  color: var(--text-color);
}

a:visited {
  color: var(--text-color);
}

img {
  display: inline-flex;
  width: 27.041px;
  height: 25.793px;
  flex-shrink: 0;
  padding-top: 45px;
  padding-right: 5px;
}

.link {
  display: flex;
  padding-right: 77px;
  flex-shrink: 0;
  justify-content: space-evenly;
}

@media screen and (max-width: 1024px) {
  #navbar {
    background-size: 15%;
    font-size: 25px;
    justify-content: flex-end;
  }
  a {
    width: 100px;
    height: 45px;
    flex-direction: row;
    white-space: nowrap;
  }
  img {
    width: 30%;
    height: 30%;
    padding-top: 30px;
    padding-right: 3px;
  }
  .link {
    padding-right: 35px;
  }
  #donate {
    padding-left: 30px;
  }
}

@media screen and (max-width: 768px) {
  #navbar {
    background-size: 15%;
    font-size: 20px;
    justify-content: flex-end;
  }
  a {
    width: 77px;
    height: 9px;
    flex-direction: row;
    white-space: nowrap;
  }
  img {
    width: 30%;
    height: 40%;
    padding-top: 23px;
    padding-right: 3px;
  }
  .link {
    padding-top: 3px;
    padding-bottom: 10px;
    padding-right: 35px;
    justify-content: space-evenly;
  }
  #donate {
    padding-left: 30px;
  }
}

@media screen and (max-width: 425px) {
  #navbar {
    background-size: 20%;
    font-size: 15px;
    justify-content: center;
  }
  a {
    width: 25px;
    height: 9px;
    padding-top: 20px;
    flex-direction: row;
    white-space: nowrap;
  }
  img {
    width: 30%;
    height: 30%;
    padding-top: 23px;
    padding-right: 3px;
  }
  .link {
    padding-top: 30px;
    padding-right: 30px;
    justify-content: space-evenly;
  }
  #donate {
    padding-left: 25px;
  }
}

@media screen and (max-width: 320px) {
  #navbar {
    background-size: 20%;
    font-size: 13px;
    justify-content: center;
  }
  a {
    width: 20px;
    height: 5px;
    padding-top: 20px;
    flex-direction: row;
    white-space: nowrap;
  }
  img {
    width: 25%;
    height: 25%;
    padding-top: 23px;
    padding-right: 0px;
  }
  .link {
    padding-top: 20px;
    padding-right: 20px;
    justify-content: space-evenly;
  }
}
</style>

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
  font-size: 2rem;
  font-weight: 400;
  letter-spacing: 0.04rem;
  background: no-repeat url(../assets/NavBar-Icons/pta-logo.png);
}

a {
  display: flex;
  width: 10.24rem;
  height: 2.56rem;
  padding-top: 1.875rem;
  padding-bottom: 2.188rem;
  flex-direction: row;
  white-space: nowrap;
  flex-shrink: 0;
  text-decoration: none;
  color: var(--text-color);
}

a:visited {
  color: var(--text-color);
}

img {
  display: inline-flex;
  width: 1.69rem;
  height: 1.612rem;
  flex-shrink: 0;
  padding-top: 2.7rem;
  padding-right: 0.313rem;
}

.link {
  display: flex;
  padding-right: 4.813rem;
  flex-shrink: 0;
  justify-content: space-evenly;
}

@media screen and (max-width: 1400px) {
  #navbar {
    background-size: 20%;
    font-size: 3rem;
    justify-content: flex-end;
  }
  a {
    width: 10rem;
    height: 3rem;
    padding-top: 3rem;
    padding-bottom: 4rem;
  }
  img {
    width: 30%;
    height: 30%;
    padding-top: 4rem;
    padding-right: 0.188rem;
  }
  .link {
    padding-right: 3rem;
  }
  #donate {
    padding-left: 6rem;
  }
}

@media screen and (max-width: 1200px) {
  #navbar {
    font-size: 2.5rem;
  }
  a {
    width: 7.5rem;
    height: 2rem;
    padding-top: 2.5rem;
  }
  img {
    padding-top: 3.2rem;
  }
}

@media screen and (max-width: 992px) {
  #navbar {
    font-size: 2rem;
  }
  a {
    width: 4rem;
    height: 2rem;
    padding-top: 2.2rem;
  }
  img {
    padding-top: 2.6rem;
  }
  .link {
    padding-right: 4.5rem;
  }
  #donate {
    padding-left: 5rem;
  }
}

@media screen and (max-width: 768px) {
  #navbar {
    background-size: 18%;
    font-size: 1.5rem;
  }
  a {
    width: 4.6rem;
    height: 0.5rem;
    padding-top: 1.5rem;
  }
  img {
    width: 30%;
    height: 30%;
    padding-top: 1.7rem;
  }
  .link {
    padding-right: 2.188rem;
  }
  #donate {
    padding-left: 1.875rem;
  }
}

@media screen and (max-width: 576px) {
  a {
    width: 2rem;
    height: 0.563rem;
    padding-top: 0.5rem;
    flex-direction: row;
    white-space: nowrap;
  }
  img {
    width: 30%;
    height: 30%;
    padding-top: 1rem;
    padding-right: 0.188rem;
  }
  .link {
    padding-top: 0.2rem;
    padding-right: 2rem;
    justify-content: space-evenly;
  }
  #donate {
    padding-left: 3.25rem;
  }
  #contact {
    padding-left: 1rem;
  }
}
</style>

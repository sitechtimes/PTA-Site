<template>
  <div id="navbar">
    <div class="link" id="home">
      <p>
        <NuxtLink to="/">Home</NuxtLink>
      </p>
    </div>
    <div class="link" id="events">
      <p>
        <NuxtLink to="/Events">Events</NuxtLink>
      </p>
    </div>
    <div class="link" id="contact">
      <img src="../assets/NavBar-Icons/envelope.svg" alt="" />
      <p>
        <NuxtLink to="/ContactUs">Contact Us</NuxtLink>
      </p>
    </div>
    <div class="link" id="donate">
      <p>
        <NuxtLink to="/Donate">Donate</NuxtLink>
      </p>
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
  flex-direction: column;
  flex-shrink: 0;
  text-decoration: none;
}

a:visited {
  color: var(--text-color);
}
img {
  display: inline-flex;
  width: 27.041px;
  height: 25.793px;
  flex-shrink: 0;
}
#events {
  width: 189.057px;
  height: 40.966px;
  flex-shrink: 0;
}
.link {
  display: inline-flex;
  justify-content: space-evenly;
  padding: 0px 77px;
  flex-shrink: 0;
}
</style>

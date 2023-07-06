<template>
  <div id="navbar">
    <div id="home">
      <h4><NuxtLink to="/">Home</NuxtLink></h4>
    </div>
    <div id="events">
      <h4><NuxtLink to="/Events">Events</NuxtLink></h4>
    </div>
    <div id="contact">
      <h4><NuxtLink to="/ContactUs">Contact Us</NuxtLink></h4>
    </div>
    <div id="donate">
      <h4><NuxtLink to="/Donate">Donate</NuxtLink></h4>
    </div>
  </div>
</template>

<style scoped>
#navbar {
  display: flex;
  flex-shrink: 0;
  justify-content: flex-end;
}
h4 {
  display: flex;
  width: 93px;
  height: 27px;
  flex-direction: column;
  flex-shrink: 0;
}
#home {
  display: inline-flex;
  width: 116px;
  height: 27px;
  flex-shrink: 0;
}
#events {
  display: inline-flex;
  width: 116px;
  height: 27px;
  flex-shrink: 0;
}
#contact {
  display: inline-flex;
  width: 116px;
  height: 27px;
  flex-shrink: 0;
}
#donate {
  display: inline-flex;
  width: 116px;
  height: 27px;
  flex-shrink: 0;
}
</style>

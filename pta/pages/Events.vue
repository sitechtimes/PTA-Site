<template>
  <section class="container__Events">
    <div id="gradient">
      <h2>EVENTS</h2>
      <EventsComponent />
      <div id="calendar">
        <h4 id="temporary">
          Google Calendar Filler to make a google Calendar, you need to make a
          public calendar for the pta to use and then use the code from that
          calendar in here.
        </h4>
      </div>
      <ScrollTop />
    </div>
  </section>
</template>

<style scoped>
@import url(../assets/base.css);

.container__Events{
  height: 180vh;
}

h2 {
  display: flex;
  justify-content: left;
  color: var(--text-color);
  font-family: Kumbh Sans;
  font-size: 400%;
  margin: 10% 0 0 5%;
}

#gradient {
  width: 100vw;
  height: 180vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: linear-gradient(180deg,
      #ffc498 0%,
      #ffd88c 20%,
      #fce5ac 34%,
      #fbefd7 44%,
      #fff 55%);
  overflow-x: hidden;
}

#calendar {
  display: flex;
  width: 65%;
  height: 25%;
  flex-direction: column;
  justify-content: center;
  margin: 10%;
  background-color: #d9d9d9;
}

#temporary {
  color: #000;
  text-align: center;
  font-size: 1.3rem;
  letter-spacing: 0.44px;
}

h6 {
  font-size: 1.2rem;
  color: #000;
  text-align: center;
}

@media screen and (max-width: 1400px) {
  h2 {
    font-size: 300%;
    margin: 5%;
  }

  .events {
    margin: 3% 5%;
    width: 59.7%;
    height: 18.31%;
  }

  #gradient {
    width: 100vw;
    height: 140vh;
  }

  #calendar {
    width: 80%;
    height: 25%;
    margin: 10% auto;
  }
}

@media screen and (max-width: 1200px) {}

@media screen and (max-width: 992px) {}

@media screen and (max-width: 768px) {}

@media screen and (max-width: 576px) {
  h2 {
    font-size: 30px;
  }

  #gradient {
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
    background: linear-gradient(180deg,
        #ffc498 0%,
        #ffd88c 20%,
        #fce5ac 34%,
        #fbefd7 44%,
        #fff 55%);
  }
}
</style>

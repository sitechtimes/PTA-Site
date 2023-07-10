<template>
  <div id="gradient">
    <div id="futureHeader"><h6>header</h6></div>
    <h2>EVENTS</h2>
    <div class="events">
      <h4 id="temporary">events filler</h4>
      <!-- <EventsComponent></EventsComponent> -->
    </div>
    <section id="calendar">
      <h4 id="temporary">
        Google Calendar Filler to make a google Calendar, you need to make a
        public calendar for the pta to use and then use the code from that
        calendar in here.
      </h4>
    </section>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);
h2 {
  display: flex;
  justify-content: left;
  color: #483221;
  font-family: Kumbh Sans;
  font-size: 400%;
  font-weight: 800;
  letter-spacing: 3.5px;
  margin: 5%;
}
.events {
  display: flex;
  margin: 3% 5%;
  width: 59.7%;
  height: 18.31%;
  background-color: #d9d9d9;
  flex-direction: row;
  justify-content: left;
}
#futureHeader {
  margin: 20px;
  height: 118px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#gradient {
  width: 100vw;
  height: 108vw;
  margin: 0;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: linear-gradient(
    180deg,
    #ffc498 0%,
    #ffd88c 20%,
    #fce5ac 34%,
    #fbefd7 44%,
    #fff 55%
  );
}
#calendar {
  display: flex;
  width: 65%;
  height: 25%;
  flex-direction: column;
  justify-content: center;
  margin: 10% auto;
  background-color: #d9d9d9;
}
#temporary {
  color: #000;
  text-align: center;
  font-size: 22px;
  letter-spacing: 0.44px;
}
h6 {
  font-size: 20px;
  color: #000;
  text-align: center;
}

@media screen and (max-width: 1100px) {
  h2 {
    font-size: 400%;
    letter-spacing: 3.5px;
    margin: 5%;
  }
  .events {
    margin: 3% 5%;
    width: 59.7%;
    height: 18.31%;
  }
  #futureHeader {
    margin: 0.2%;
    height: 10%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #gradient {
    width: 100vw;
    height: 108vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
    background: linear-gradient(
      180deg,
      #ffc498 0%,
      #ffd88c 20%,
      #fce5ac 34%,
      #fbefd7 44%,
      #fff 55%
    );
  }
  #calendar {
    display: flex;
    width: 65%;
    height: 25%;
    flex-direction: column;
    justify-content: center;
    margin: 10% auto;
    background-color: #d9d9d9;
  }
  #temporary {
    color: #000;
    text-align: center;
    font-size: 22px;
    letter-spacing: 0.44px;
  }
}
@media screen and (max-width: 390px) {
}
</style>

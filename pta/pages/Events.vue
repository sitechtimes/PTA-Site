<template>
  <div id="gradient">
    <h2>EVENTS</h2>
    <EventsComponent></EventsComponent>
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
  color: var(--text-color);
  font-family: Kumbh Sans;
  font-size: 400%;
  margin: 5%;
  margin-top: 10%;
  padding-left: 2rem;
}

#gradient {
  width: 100%;
  height: 180vh;
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
    margin-top: 13%;
  }
  #gradient {
    height: 140vh;
  }
  #calendar {
    width: 80%;
    height: 25%;
    margin: 10% auto;
  }
}
@media screen and (max-width: 1200px) {
  h2 {
    margin-top: 15%;
  }
}
@media screen and (max-width: 992px) {
  h2 {
    margin-top: 18%;
  }
}
@media screen and (max-width: 768px) {
  h2 {
    margin-top: 16%;
  }
}
@media screen and (max-width: 576px) {
  h2 {
    font-size: 40px;
    margin-top: 6rem;
  }
  #gradient {
    width: 100vw;
    height: 100vh;
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
  @media screen and (max-width: 356px) {
    h2 {
      font-size: 30px;
      margin-top: 6rem;
    }
  }
}
</style>

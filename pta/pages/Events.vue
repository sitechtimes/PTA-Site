<template>
  <section id="gradient">
    <div id="futureHeader"><h6>header</h6></div>
    <h2>EVENTS</h2>
    <div class="events">
      <EventsComponent></EventsComponent>
    </div>
  </section>
  <section id="calendar">
    <h4 id="temporary">Google Calendar Filler</h4>
  </section>
  <div id="futureFooter"><h6>footer</h6></div>
</template>

<style scoped>
@import url(../assets/base.css);
h2 {
  display: flex;
  width: 1061px;
  height: 161px;
  flex-direction: column;
  justify-content: center;
  color: #483221;
  font-family: Kumbh Sans;
  font-size: 70px;
  font-style: normal;
  font-weight: 800;
  line-height: 129.164%;
  letter-spacing: 3.5px;
  margin-left: 106px;
}
.events {
  margin: 35px 96px;
  width: 1146.093px;
  height: 365px;
  background-color: #d9d9d9;
}
#futureHeader {
  margin: 20px;
  height: 118px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#gradient {
  height: 1061px;
  background: linear-gradient(
    180deg,
    #ffc498 0%,
    #ffd88c 28.65%,
    #ffd88c 61.98%,
    #fce5ac 81.25%,
    #fff 98.95%,
    #fff 98.96%
  );
}
#calendar {
  display: flex;
  width: 1289px;
  height: 495px;
  flex-direction: column;
  justify-content: center;
  margin: 0px 315px;
  width: 1289px;
  height: 495px;
  background-color: #d9d9d9;
}
#temporary {
  color: #000;
  text-align: center;
  font-size: 22px;
  font-weight: 0.5;
  letter-spacing: 0.44px;
}
#futureFooter {
  width: 1920px;
  height: 249px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
h6 {
  font-size: 20px;
  color: #000;
  text-align: center;
  font-weight: 0.5;
}
</style>

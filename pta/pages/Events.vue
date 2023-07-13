<template>
  <head>
    <title>Events Page</title>
    <html lang="en"></html>
  </head>
  <section class="container__Events">
    <div id="gradient">
      <h1>EVENTS</h1>
      <h2>Upcoming Events:</h2>
      <EventsComponent />
      <div id="calendarParent">
        <div id="calendar">
          <h4 id="temporary">
            Google Calendar Filler to make a google Calendar, you need to make a
            public calendar for the pta to use and then use the code from that
            calendar in here.
          </h4>
        </div>
      </div>
      <ScrollTop />
    </div>
  </section>
</template>

<style scoped>
@import url(../assets/base.css);

.container__Events {
  height: 180vh;
}

h1 {
  display: flex;
  justify-content: left;
  color: var(--text-color);
  font-family: Kumbh Sans;
  font-size: 400%;
  margin: 5%;
  margin-top: 10%;
  padding-left: 2rem;
}
h2 {
  color: var(--text-color);
  font-family: Kumbh Sans;
  margin: 5%;
  padding-left: 2rem;
}
#gradient {
  width: 100vw;
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
  height: 100%;
  flex-direction: column;
  justify-content: center;
  background-color: #d9d9d9;
  margin-top: 10%;
}
#calendarParent {
  width: 100%;
  height: 25%;
  display: flex;
  flex-direction: column;
  align-items: center;
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
  h1 {
    font-size: 300%;
    margin: 5%;
    margin-top: 13%;
  }

  #gradient {
    height: 140vh;
  }
}

@media screen and (max-width: 1200px) {
  h1 {
    margin-top: 15%;
  }
}

@media screen and (max-width: 992px) {
  h1 {
    margin-top: 18%;
  }
  h2 {
    font-size: 200%;
  }
}

@media screen and (max-width: 768px) {
  h1 {
    margin-top: 16%;
    padding-left: 1.1rem;
  }
  h2 {
    padding-left: 1.1rem;
  }
}

@media screen and (max-width: 576px) {
  h1 {
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
    #temporary {
      font-size: 15px;
    }
    h1 {
      font-size: 30px;
      margin-top: 6rem;
    }
    h2 {
      font-size: 20px;
    }
    .calendarParent {
      height: 50%;
    }
  }
}
</style>

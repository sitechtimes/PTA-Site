<template>
  <div>
    <div id="wrapper">
      <div id="gradient">
        <h1 class="heading">EVENTS</h1>
        <section id="top">
          <EventsComponent />
          <div id="calender">
            <iframe
              class="cal"
              id="calenderInner"
              src="https://calendar.google.com/calendar/embed?height=600&wkst=1&bgcolor=%23ffeacd&ctz=America%2FNew_York&src=Y184NWZkZjlkNWVkYzQzMTVjYTEzNmYyZGJhZjA0ZWQyODU5MGZiMmZlNmU2ZGQ2ZjA5MWYwY2JlYjJlYTY2MTc0QGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20&color=%23795548"
              frameborder="0"
              scrolling="no"
            ></iframe>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    gsap.from(".heading", { duration: 1, y: 100, opacity: 0 });
    gsap.from(".cal", 1, { x: 1000 }, "<0.5");
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
#calenderInner {
  border: solid 1px #777;
  width: 35vw;
  height: 30vw;
}
#wrapper {
  height: 60vw;
}
#gradient {
  width: 100vw;
  height: 180vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: var(--bg-gradient);
  overflow-x: hidden;
}
#eventsCon {
  list-style-type: none;
  padding-left: 0;
}
.uniqEvent {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
#title {
  margin: 0;
  font-family: "Kumbh Sans", sans serif;
  font-weight: bolder;
}
ul {
  overflow: auto;
  height: 27vw;
}
.listTitle,
.listDate {
  margin-right: 1vw;
  font-weight: 400;
}
.listTitle {
  width: 20vw;
}
.listDate {
  text-align: end;
}
#head {
  position: absolute;
  top: 70vw;
  right: 19vw;
  height: 30vw;
  padding-bottom: 10vw;
}
#upcomingEvents {
  color: var(--text-color);
  font-family: Kumbh Sans;
}
::-webkit-scrollbar {
  width: 0px;
  background: transparent; /* make scrollbar transparent */
}
li {
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 2vw;
  border-radius: 1vw;
  width: 35vw;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
}

#top {
  display: flex;
  justify-content: space-evenly;
  flex-direction: row;
  align-items: center;
}
#calender {
  width: 35vw;
  /* background-color: white; */
  border-radius: 3vw;
  height: 30vw;
  /* margin-top: -2vw; */
}
@media screen and (max-width: 1400px) {
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
}

@media screen and (max-width: 992px) {
}

@media screen and (max-width: 768px) {
  .listTitle {
    width: 18vw;
  }
  #calenderInner {
    border: solid 1px #777;
    width: 35vw;
    height: 30vw;
  }
}

@media screen and (max-width: 576px) {
  #calenderInner {
    border: solid 1px #777;
    width: 80vw;
    height: 70vw;
  }
  #wrapper {
    height: 170vw;
  }
  #top {
    flex-direction: column;
  }
  #upcomingEvents {
    margin-bottom: 10vw;
  }
  #eventsCon {
    height: 50vw;
  }
  .uniqEvent {
    margin: 0 1rem 0 1rem;
  }
  li {
    width: 76vw;
    border-radius: 2.5vw;
    margin-bottom: 4vw;
  }
  .listTitle {
    width: 45vw;
  }
  #calender {
    width: 80%;
    height: 60vw;
  }
  #gradient {
    width: 100%;
    height: 220vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}
@media only screen and (max-width: 450px) {
  /* .listTitle {
    width: 40vw;
  }
  #calenderInner {
    border: solid 1px #777;
    width: 80vw;
    height: 70vw;
  } */
}
@media only screen and (max-width: 356px) {
  .uniqEvent {
    margin: 0 0.7rem 0 0.7rem;
  }
  #calenderInner {
    border: solid 1px #777;
    width: 80vw;
    height: 70vw;
  }
}
@media screen and (min-width: 576px) {
  #gradient {
    width: 100%;
    height: 100vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 576px) and (orientation: landscape) {
  #gradient {
    width: 100%;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 768px) {
  #gradient {
    width: 100%;
    height: 80vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
  #gradient {
    width: 100%;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}
</style>

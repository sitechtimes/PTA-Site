<template>
  <div id="upcomingEvents">
    <h3 class="subh" ref="subh">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        height="1em"
        viewBox="0 0 512 512"
      >
        <!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
        <path
          d="M480 32c0-12.9-7.8-24.6-19.8-29.6s-25.7-2.2-34.9 6.9L381.7 53c-48 48-113.1 75-181 75H192 160 64c-35.3 0-64 28.7-64 64v96c0 35.3 28.7 64 64 64l0 128c0 17.7 14.3 32 32 32h64c17.7 0 32-14.3 32-32V352l8.7 0c67.9 0 133 27 181 75l43.6 43.6c9.2 9.2 22.9 11.9 34.9 6.9s19.8-16.6 19.8-29.6V300.4c18.6-8.8 32-32.5 32-60.4s-13.4-51.6-32-60.4V32zm-64 76.7V240 371.3C357.2 317.8 280.5 288 200.7 288H192V192h8.7c79.8 0 156.5-29.8 215.3-83.3z"
        />
      </svg>
      Upcoming Events
    </h3>
    <ul class="subtext" id="eventsCon">
      <li
        v-for="event in events"
        :key="event"
        id="uniqEvent"
        class="li"
        ref="li"
      >
        <NuxtLink to="/Events" @click="(page='Events'), underline()" id="eventsLink" ref="eventsLink">
          <div class="uniqEvent">
            <h5 class="listTitle">{{ event.title }}</h5>
            <h5 class="listDate">
              {{ event.month }}/{{ event.date }}/{{ event.year }}
            </h5>
          </div></NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from "vue";
import { gsap } from "gsap";

export default {
  data() {
    return {
      events: Array,
    };
  },
  methods: {
    underline() {
      if (this.page === "index") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "underline var(--text-color) 0.2rem";
        this.eventsLine = "transparent";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      } else if (this.page === "Events") {
        console.log(this.page);
        this.fade = "fadeIn 5s;";
        this.homeLine = "transparent";
        this.eventsLine = "underline var(--text-color) 0.2rem";
        this.contactLine = "transparent";
        this.gratitudeLine = "transparent";
        this.donateLine = "transparent";
      }
  },
    async getEvents() {
      const query = queryContent("/events").find();
      console.log(query);
      query.then((response) => {
        this.events = response;
        nextTick(() => {
          gsap.from("li", {
            delay: 0.9,
            duration: 0.5,
            y: 100,
            opacity: 0,
            stagger: 0.3,
          });
          console.log("gsap");
        });
      });
    },
  },
  mounted() {
    this.getEvents();
    const { li } = this.$refs;
    const { subh } = this.$refs;
    gsap.from(li, {
      delay: 1.2,
      duration: 0.5,
      x: 7,
      opacity: 0,
      stagger: 0.3,
    });
    gsap.from(subh, { delay: 1, duration: 0.5, x: 7, opacity: 0 });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
svg {
  fill: var(--text-color);
  margin-right: 2%;
}
.subh {
  margin-top: 1.5rem;
  width: 32vw;
}
#eventsCon {
  list-style-type: none;
  padding-left: 0;
  /* width: 32vw; */
  -ms-overflow-style: none;
  scrollbar-width: none;
}

#upcomingEvents {
  width: 32vw;
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.uniqEvent {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  color: var(--text-color);
}
a:link {
  text-decoration: none;
}
ul {
  overflow: auto;
  -ms-overflow-style: none;
  height: 25vw;
  scrollbar-width: none;
}
.listTitle,
.listDate {
  margin-right: 1vw;
  font-weight: 400;
}
.listTitle {
  width: 10vw;
}
.listDate {
  text-align: end;
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
  width: 25vw;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
}
@media only screen and (max-width: 1400px) {
  .subh {
    margin-top: 2rem;
    width: 40vw;
  }
  #upcomingEvents {
    margin-top: 5rem;
    margin-top: 1.5rem;
    font-size: 2rem;
    width: 40vw;
  }
}
@media screen and (max-width: 1200px) {
  .subh {
    margin-top: 2rem;
    width: 40vw;
  }
  #upcomingEvents {
    margin-top: 8vw;
    margin-left: 4rem;
  }
  #eventsCon {
    height: 19vw;
  }
  .listTitle,
  .listDate {
    font-size: 1.7vw;
    width: 15vw;
  }
  li {
    width: 30vw;
  }
}
@media screen and (max-width: 992px) {
  #upcomingEvents {
    width: 40vw;
    height: 50vw;
    margin-top: 40%;
    margin-left: 25%;
  }
  #eventsCon {
    width: 40vw;
    height: 19vw;
  }
  .subh {
    width: 40vw;
  }
  .listTitle {
    width: 30vw;
  }
  li {
    width: 30vw;
  }
}
@media screen and (max-width: 768px) {
  #upcomingEvents {
    width: 75vw;
  }
  .subh {
    width: 75vw;
  }
  #eventsCon {
    height: 18rem;
  }

  li {
    width: 55vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 1.03rem;
  }
}
@media screen and (max-width: 768px) {
  #upcomingEvents {
    width: 40vw;
    margin-top: 50%;
    margin-left: 30%;
  }
  #eventsCon {
    width: 40vw;
    height: 20vw;
  }
  .subh {
    width: 35vw;
    margin-bottom: 0.8rem;
  }
  .listTitle {
    width: 35vw;
  }
  .listTitle,
  .listDate {
    font-size: 1.8vw;
    margin-top: 3vw;
    margin-bottom: 3vw;
  }
  li {
    width: 30vw;
  }
}
@media only screen and (max-width: 576px) {
  #upcomingEvents {
    margin-left: 12%;
    margin-top: 40%;
    width: 100vw;
    margin-right: 12%;
  }
  svg {
    margin-right: 1%;
  }
  ::-webkit-scrollbar {
    width: 0px;
    background: transparent; /* make scrollbar transparent */
  }
  .subh {
    width: 75vw;
  }
  #eventsCon {
    height: 17.5rem;
    width: 100.1%;
  }
  .uniqEvent {
    margin: 0 1rem 1.5rem 1rem;
  }
  li {
    width: 68vw;
    border-radius: 2vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 3vw;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
  }
}
@media only screen and (max-width: 450px) {
  .listTitle,
  .listDate {
    font-size: 3.7vw;
  }
  .listDate {
    width: 20vw;
  }
  #upcomingEvents {
    margin-top: 45%;
    padding-left: 0.1rem;
  }
}
@media only screen and (max-width: 356px) {
  #upcomingEvents {
    width: 71vw;
    margin-top: 48%;
  }
  #eventsCon {
    height: 15.35rem;
  }
  .subh {
    font-size: 6vw;
  }
  .uniqEvent {
    margin: 0 1rem 1rem 1rem;
  }
  li {
    width: 64vw;
  }
}
</style>

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
        <div class="uniqEvent">
          <h5 class="listTitle">{{ event.title }}</h5>
          <h5 class="listDate">{{ event.date }}</h5>
        </div>
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
    async getEvents() {
      const query = queryContent("/events").find();
      console.log(query);
      query.then((response) => {
        this.events = response;
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
@media screen and (max-width: 1400px) {
  .subh {
    margin-top: 2rem;
    font-size: 1.5rem;
    width: 28vw;
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
    font-size: 1.5rem;
    width: 40vw;
  }
  #upcomingEvents {
    margin-top: 13vw;
  }
}
/*
@media screen and (max-width: 1200px) {
  #upcomingEvents {
    height: 50vw;
  }
  #eventsCon {
    height: 25vw;
  }
  .subh {
    font-size: 3vw;
  }
  .listTitle,
  .listDate {
    font-size: 2vw;
  }
}

@media screen and (max-width: 1200px) and (orientation: landscape) {
  #upcomingEvents {
    width: 38vw;
    height: 50vw;
  }
  #eventsCon {
    width: 38vw;
    height: 30vw;
  }
  .subh {
    font-size: 3vw;
    width: 38vw;
  }
  .listTitle {
    width: 30vw;
  }
  .listTitle,
  .listDate {
    font-size: 1.5vw;
  }
  li {
  }
} */

@media screen and (max-width: 992px) {
  #upcomingEvents {
    width: 72vw;
    height: 50vw;
    margin-top: 45%;
  }
  #eventsCon {
    width: 73.5vw;
    height: 19vw;
    overflow-x: hidden;
  }
  .subh {
    margin-top: 1rem;
    font-size: 1.5rem;
    width: 73.5vw;
  }
  .listTitle {
    width: 30vw;
  }
  .listTitle,
  .listDate {
    font-size: 2vw;
  }
  li {
    width: 29rem;
  }
}

@media screen and (max-width: 992px) and (orientation: landscape) {
  #upcomingEvents {
    width: 40vw;
    height: 50vw;
    margin-top: 50%;
  }
  #eventsCon {
    width: 40vw;
    height: 30vw;
  }
  .subh {
    font-size: 3vw;
    width: 40vw;
  }
  .listTitle {
    width: 30vw;
  }
  .listTitle,
  .listDate {
    font-size: 1.7vw;
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
    font-size: 5vw;
    width: 75vw;
  }
  #eventsCon {
    height: 18rem;
  }
  .uniqEvent {
    margin: 0 1rem 1rem 1rem;
  }
  li {
    width: 55vw;
    border-radius: 2.5vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 1.03rem;
  }
}

@media screen and (max-width: 768px) and (orientation: landscape) {
  #upcomingEvents {
    width: 45vw;
    margin-top: 2rem;
  }
  #eventsCon {
    width: 45vw;
    height: 31vw;
  }
  .subh {
    font-size: 3vw;
    width: 45vw;
  }
  .listTitle {
    width: 30vw;
  }
  .listTitle,
  .listDate {
    font-size: 1.5vw;
  }
  li {
    width: 15rem;
  }
}

@media screen and (max-width: 576px) {
  svg {
    margin-right: 1%;
  }
  ::-webkit-scrollbar {
    width: 0px;
    background: transparent; /* make scrollbar transparent */
  }
  #upcomingEvents {
    margin-top: 3rem;
    width: 75vw;
  }
  .subh {
    font-size: 5vw;
    width: 75vw;
  }
  #eventsCon {
    height: 54vw;
    width: 80vw;
  }
  .uniqEvent {
    margin: 0 1rem 1rem 1rem;
  }
  li {
    width: 68vw;
    border-radius: 2vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 3vw;
  }
}
@media only screen and (max-width: 356px) {
  #upcomingEvents {
    width: 70vw;
  }
  li {
    width: 64vw;
  }
}
</style>

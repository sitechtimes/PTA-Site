<template>
  <div id="upcomingEvents">
    <h3 class="subh">Upcoming Events</h3>
    <ul class="subtext" id="eventsCon">
      <li v-for="(event, index) in upcomingEvents" :key="index" id="uniqEvent">
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
  components: {},
  setup() {
    const upcomingEvents = ref([
      {
        title: "Jessie's Birthday",
        date: "05/23/2023",
        body: "<3",
      },
      {
        title: "Bake Sale",
        date: "05/27/2023",
        body: "<3",
      },
      {
        title: "Very Long Named Event",
        date: "05/30/2023",
        body: "<3",
      },
      {
        title: "Super Duper Very Extremely Long Named Event",
        date: "05/31/2023",
        body: "<3",
      },
    ]);

    return {
      upcomingEvents,
    };
  },
  mounted() {
    gsap.from(".subh", { delay: 0.5, duration: 1, x: 1000, opacity: 0 });
    gsap.from("li", { delay: 0.7, duration: 0.5, y: 100, opacity: 0 });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
.subh {
  margin-top: 1.5rem;
  width: 32vw;
}
#eventsCon {
  list-style-type: none;
  padding-left: 0;
  /* width: 32vw; */
}

#upcomingEvents {
  width: 32vw;
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
  scrollbar-width: none;
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
    width: 40vw;
    height: 50vw;
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
    font-size: 1.5vw;
  }
  li {
  }
} */

@media screen and (max-width: 992px) {
  #upcomingEvents {
    width: 72vw;
    height: 50vw;
    margin-top: 41%;
  }
  #eventsCon {
    width: 73.5vw;
    height: 32vw;
  }
  .subh {
    font-size: 3vw;
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
    width: 17rem;
  }
}

@media screen and (max-width: 768px) {
  #upcomingEvents {
    width: 75vw;
    margin-top: 15rem;
  }
  .subh {
    font-size: 5vw;
    width: 75vw;
  }
  #eventsCon {
    width: 75vw;
    height: 15.5rem;
  }
  /* .uniqEvent {
    margin: 0 1rem 1rem 1rem;
  } */
  li {
    width: 55vw;
    border-radius: 2.5vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 1rem;
  }
}

@media screen and (max-width: 768px) and (orientation: landscape) {
  #upcomingEvents {
    width: 45vw;
    height: 50vw;
  }
  #eventsCon {
    width: 45vw;
    height: 30vw;
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
  #upcomingEvents {
    margin-top: 0;
    width: 75vw;
  }
  .subh {
    font-size: 5vw;
    width: 75vw;
  }
  #eventsCon {
    height: 38vh;
    width: 75vw;
  }
  .uniqEvent {
    margin: 0 1rem 1rem 1rem;
  }
  li {
    width: 68vw;
    border-radius: 2.5vw;
  }
  .listTitle,
  .listDate {
    width: 30vw;
    font-size: 3vw;
  }
}
</style>

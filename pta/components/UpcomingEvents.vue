<template>
  <div id="upcomingEvents">
    <h3 class="subh">Upcoming Events</h3>
    <ul class="subtext" id="eventsCon">
      <li
        v-for="(event, index) in upcomingEvents"
        :key="index"
        @click="() => selectEvent(event)"
        class="uniqEvent"
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
      selectedEvent,
      selectEvent,
    };
  },
  mounted() {
    gsap.from(".subh", { delay: 0.5, duration: 1, y: 100, opacity: 0 });
    gsap.from("li", { delay: 0.7, duration: 0.5, y: 100, opacity: 0 });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
.subh {
  margin-top: 1.5rem;
}
#wrapper {
  height: 60vw;
}
#eventsCon {
  list-style-type: none;
  padding-left: 0;
}
.uniqEvent {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
}
#title {
  margin: 0;
  font-family: "Kumbh Sans", sans serif;
  font-weight: bolder;
}
ul {
  overflow: auto;
  -ms-overflow-style: none;
  scrollbar-width: none;
  height: 27vw;
  scrollbar-width: none;
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

@media screen and (max-width: 768px) {
  .listTitle {
    width: 18vw;
  }
}

@media screen and (max-width: 576px) {
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
}
@media only screen and (max-width: 450px) {
  .listTitle {
    width: 40vw;
  }
}
@media only screen and (max-width: 356px) {
  .uniqEvent {
    margin: 0 0.7rem 0 0.7rem;
  }
}
</style>

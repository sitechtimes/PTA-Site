<template>
  <div>
    <!-- <p>{{ event.title }}</p> -->
    <div v-for="event in eventCollection" :key="event.slug">
      <h1>{{ event.title }}</h1>
    </div>
    <Popup
      v-if="popupTriggers.buttonTrigger"
      :TogglePopup="() => TogglePopup('buttonTrigger')"
      :event="selectedEvent"
    >
      <h5 class="text" id="title">{{ selectedEvent.title }}</h5>
      <p class="text" id="date">
 {{ selectedEvent.month }}/{{ selectedEvent.date }}/{{selectedEvent.year }}
      </p>
      <p class="text" id="time">{{ selectedEvent.time }}</p>
      <img id="img" :src="selectedEvent.image" alt="" />
      <p class="text" id="body">{{ selectedEvent.description }}</p>
    </Popup>
    <div id="upcomingEvents">
      <h3 class="subh">Upcoming Events</h3>
      <ul class="subtext" id="eventsCon">
        <li
          v-for="event in events"
          @click="() => selectEvent(event)"
          class="uniqEvent"
        >
          <div class="uniqEvent">
            <h5 class="listTitle">{{ event.title }}</h5>
            <h5 class="listDate"> {{ event.month }}/{{ event.date }}/{{ event.year }}</h5>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import { ref, onMounted } from "vue";
import Popup from "../components/Popup.vue";
import { gsap } from "gsap";

export default {
  components: {
    Popup,
  },
  data() {
    return {
      events: Array,
      create: false,
    };
  },
  methods: {
    async getEvents() {
      const query = queryContent("/events").find();
      console.log(query);
      query.then((response) => {
        console.log(response);
        this.events = response;
        this.create = true;
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
  setup() {
    const post = ref(null);
    const selectedEvent = ref(null);

    const selectEvent = (event) => {
      selectedEvent.value = event;
      TogglePopup("buttonTrigger"); // Open the popup
    };
    const popupTriggers = ref({
      buttonTrigger: false,
      timedTrigger: false,
    });

    const TogglePopup = (trigger) => {
      popupTriggers.value[trigger] = !popupTriggers.value[trigger];
    };

    setTimeout(() => {
      popupTriggers.value.timedTrigger = true;
    }, 3000);

    const eventCollection = ref([]);

    onMounted(async () => {
      const { $content } = await import("@nuxt/content");
      eventCollection.value = await $content("events").fetch();
    });

    return {
      Popup,
      popupTriggers,
      TogglePopup,
      selectedEvent,
      selectEvent,
      eventCollection,
    };
  },
  mounted() {
    this.getEvents();
    gsap.from(".subh", { delay: 0.5, duration: 0.7, y: 100, opacity: 0 });
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
  overflow-x: hidden;
  padding-left: 0;
}
.uniqEvent {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  width: 34.5vw;
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
  height: 24vw;
  scrollbar-width: none;
}
.listTitle,
.listDate {
  margin-right: 1vw;
  font-weight: 400;
}
.listTitle {
  width: fit-content;
  width: 15vw;
}
.listDate {
  width: 20vw;
  text-align: right;
  /* flex-direction: row;
  align-self: flex-end; */
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
  background-color: white;
  border-radius: 3vw;
  height: 30vw;
  /* margin-top: -2vw; */
}
@media only screen and (max-width: 1400px) {
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

@media only screen and (max-width: 768px) {
  .listTitle {
    width: 20vw;
  }
  .listDate {
    width: 15vw;
  }
  ul {
    height: 21vw;
  }
}

@media only screen and (max-width: 576px) {
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
    height: 55vw;
  }
  .uniqEvent {
    width: 70vw;
  }
  li {
    width: 76vw;
    border-radius: 2.5vw;
    margin-bottom: 4vw;
    padding: 0vw 6vw 0vw 6vw;
  }
  .listTitle {
    width: 20vw;
  }
  .listDate {
    width: 20vw;
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
  .subh {
    margin: 1.5rem 0 0 0;
  }
}
@media only screen and (max-width: 450px) {
  .listTitle {
    width: 55vw;
  }
  #eventsCon {
    height: 60vw;
  }
}
@media only screen and (max-width: 356px) {
  #eventsCon {
    height: 66vw;
  }
}
@media only screen and (min-width: 576px) {
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

@media only screen and (min-width: 576px) and (orientation: landscape) {
  #gradient {
    width: 100%;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
}

@media only screen and (min-width: 768px) {
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

@media only screen and (min-width: 768px) and (orientation: landscape) {
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

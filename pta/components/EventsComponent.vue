<template>
  <div>
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
        {{ selectedEvent.month }}/{{ selectedEvent.date }}/{{
          selectedEvent.year
        }}
      </p>
      <p class="text" id="time">{{ selectedEvent.time }}</p>
      <img id="img" :src="selectedEvent.image" alt="" />
      <p class="text" id="body">{{ selectedEvent.description }}</p>
      <div class="btnCon">
        <a :href="selectedEvent.volunteer" target="_blank">
          <button class="btn" id="reg">Volunteer</button>
        </a>
        <a :href="selectedEvent.signup" target="_blank">
          <button class="btn btn2" id="reg">Register</button>
        </a>
        <a :href="selectedEvent.donate" target="_blank">
          <button class="btn" id="reg">Donate</button>
        </a>
      </div>
    </Popup>
    <div id="upcomingEvents">
      <h3 class="subh">Upcoming Events</h3>
      <ul class="subtext" id="eventsCon">
        <li
          v-for="event in sortedEvents"
          @click="() => selectEvent(event)"
          class="uniqEvent"
        >
          <div class="uniqEvent">
            <h5 class="listTitle">{{ event.title }}</h5>
            <h5 class="listDate">
              {{ event.month }}/{{ event.date }}/{{ event.year }}
            </h5>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, nextTick, onMounted } from "vue";
import Popup from "../components/Popup.vue";
import { gsap } from "gsap";

const events = ref([]);
const selectedEvent = ref(null);
const popupTriggers = ref({
  buttonTrigger: false,
  timedTrigger: false,
});
const eventCollection = ref([]);

const sortedEvents = computed(() => {
  const today = new Date();
  
  return events.value
  //each event is rewritten to be yyyy-mm-dd
    .filter((event) => {
      const eventDate = new Date(`${event.year}-${event.month}-${String(event.date).padStart(2, '0')}`);
      return eventDate >= today;
    })
    .sort((a, b) => { 
      const dateA = new Date(`${a.year}-${a.month}-${String(a.date).padStart(2, '0')}`);
      const dateB = new Date(`${b.year}-${b.month}-${String(b.date).padStart(2, '0')}`);
      return dateA - dateB;
    });
});

const getEvents = async () => {
  const response = await queryContent("/events").find();
  events.value = response;

  nextTick(() => {
    gsap.from("li", {
      delay: 0.9,
      duration: 0.5,
      y: 100,
      opacity: 0,
      stagger: 0.3,
    });
  });
};


const selectEvent = (event) => {
  selectedEvent.value = event;
  TogglePopup("buttonTrigger");
};

const TogglePopup = (trigger) => {
  popupTriggers.value[trigger] = !popupTriggers.value[trigger];
};

onMounted(() => {
  getEvents();
  gsap.from(".subh", { delay: 0.5, duration: 0.7, y: 100, opacity: 0 });

  setTimeout(() => {
    popupTriggers.value.timedTrigger = true;
  }, 3000);

  import("@nuxt/content").then(({ $content }) => {
    $content("events").fetch().then((data) => {
      eventCollection.value = data;
    });
  });
});
</script>

<style scoped>
@import url(../assets/base.css);
.btn2 {
  margin-left: 1rem;
  margin-right: 1rem;
}
.btn {
  width: 8rem;
  padding: 0.7rem 1rem 0.7rem 1rem;
}
.btnCon {
  display: flex;
}
.subh {
  margin-top: 1.5rem;
  display: flex;
  justify-content: space-between;
}
#wrapper {
  height: 60vw;
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
}
#head {
  position: absolute;
  top: 70vw;
  right: 19vw;
  height: 30vw;
  padding-bottom: 10vw;
}
#body {
  margin-bottom: 1.5rem;
}
#upcomingEvents {
  color: var(--text-color);
  font-family: Kumbh Sans;
  width: fit-content;
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
#reg {
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  border-style: none;
}
@media only screen and (max-width: 1400px) {
}

@media screen and (max-width: 1200px) {
  #reg {
    font-size: 1rem;
  }
}

@media screen and (max-width: 992px) {
  .uniqEvent {
    width: 60vw;
  }
  ul {
    height: 33vw;
  }
  #reg {
    font-size: 0.9rem;
  }
  .btn {
    width: 6.5rem;
  }
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
  .btn {
    margin: 0;
    margin-bottom: 0.5rem;
  }
  .btnCon {
    flex-direction: column;
  }
  #reg {
    margin-top: 0.8rem;

    padding: 0.5rem 1rem 0.5rem 1rem;
    border-radius: 0.7rem;
    font-size: 0.9rem;
  }
  .subh {
    margin: 1.5rem 0 0 0;
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
  .subh {
    display: flex;
    flex-direction: column;
  }
  .btn2 {
    margin: 0;
  }
  .btnCon {
    flex-direction: column;
  }
  #reg {
    margin-top: 0.8rem;

    padding: 0.5rem 1rem 0.5rem 1rem;
    border-radius: 0.7rem;
    font-size: 0.9rem;
  }
  .subh {
    margin: 1.5rem 0 0 0;
  }
}
@media only screen and (max-width: 400px) {
  #reg {
    width: 80vw;
    font-size: 0.8rem;
  }
  .btnCon {
    flex-direction: column;
  }
}
</style>

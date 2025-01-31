<template>
  <div class="flex flex-col mb-6 px-6 w-full" id="upcomingEvents">
    <h2 class="font-bold text-2xl text-left my-6">UPCOMING EVENTS</h2>
    <div v-for="event in sortedEvents" :key="event.id" @click="selectEvent(event)">
      <div
        class="p-2 my-2 flex flex-row justify-between items-center h-16 w-full lg:p-8 bg-white rounded-lg font-semibold space-x-5 cursor-pointer shadow-md">
        <h3 class="text-lg md:text-xl">{{ event.title }}</h3>
        <h3 class="text-lg md:text-xl">{{ event.month }}/{{ event.date }}/{{ event.year }}</h3>
      </div>
    </div>
    <EventModal :event="selectedEvent" :close="closeModal" />
  </div>
</template>

<script setup>
import { gsap } from "gsap";

const events = ref([]);
const selectedEvent = ref(null);

const sortedEvents = computed(() => {
  const today = new Date();

  return (
    events.value
      .filter((event) => {
        const eventDate = new Date(`${event.year}-${event.month}-${String(event.date).padStart(2, "0")}`);
        return eventDate >= today;
      })
      .sort((a, b) => {
        const dateA = new Date(`${a.year}-${a.month}-${String(a.date).padStart(2, "0")}`);
        const dateB = new Date(`${b.year}-${b.month}-${String(b.date).padStart(2, "0")}`);
        return dateA - dateB;
      })
  );
});

function closeModal() {
  selectedEvent.value = null;
}

const getEvents = async () => {
  const response = await queryContent("/events").find();
  events.value = response;
};

const selectEvent = (event) => {
  selectedEvent.value = event;
};

onMounted(() => {
  getEvents();
  gsap.from("#upcomingEvents", { delay: 0.5, duration: 0.7, x: -100, opacity: 0 });
});
</script>

<template>
  <div class="w-screen h-fit py-10 flex flex-col justify-center items-center lg:justify-between lg:px-20">
    <h1 id="heading" class="text-4xl sm:text-5xl font-bold text-center">EVENTS</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 m-8 mt-16 w-full h-full px-4 lg:px-10">
      <UpcomingEvents />

      <div class="cal relative z-10">
        <iframe
          class="rounded-xl w-full h-96 md:h-full"
          id="calendarInner"
          src="https://calendar.google.com/calendar/embed?height=600&wkst=1&bgcolor=%23ffeacd&ctz=America%2FNew_York&src=Y184NWZkZjlkNWVkYzQzMTVjYTEzNmYyZGJhZjA0ZWQyODU5MGZiMmZlNmU2ZGQ2ZjA5MWYwY2JlYjJlYTY2MTc0QGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20&color=%23795548"
          frameborder="0"
          scrolling="no"
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script setup>
import { gsap } from "gsap";
import UpcomingEvents from "~/components/UpcomingEvents.vue";

onMounted(() => {
  gsap.from("#heading", { duration: 1, y: 100, opacity: 0 });
  gsap.from(".cal", { duration: 1, y: 100, delay: 0.8, opacity: 0 });
});
</script>

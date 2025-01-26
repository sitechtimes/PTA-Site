<template>
    <div v-if="event" class="fixed inset-0 z-80 flex items-center justify-center bg-black bg-opacity-50 w-full rounded-lg">
      <div class="bg-white p-6 rounded-lg w-1/3 text-center">
        <h4 class="font-bold text-lg md:text-2xl text-center">{{ event.title }}</h4>
        <p class="font-semibold italic text-md md:text-xl">
          {{ event.month }}/{{ event.date }}/{{ event.year }}
        </p>
        <p class="text-md md:text-xl my-2">{{ event.description }}</p>
        <button @click="close"
          class="bg-light-brown w-1/3 p-2 rounded-md hover:bg-dark-brown hover:transition-ease-in duration-300 text-white">
          Close
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    event: {
      type: Object,
    },
    close: {
      type: Function,
    },
  });
  </script>
  
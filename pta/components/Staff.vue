<template>
    <div class="flex flex-wrap justify-around px-2">
    <div v-for="(profile, index) in profiles"
    :key="index"
     id="profile" class="content-center w-1/2 2xl:w-1/3 my-4 flex items-center text-center text-wrap flex-col px-1">
        <img :src="profile.image" :alt="profile.name" class="rounded-full w-24 h-24 sm:w-32 sm:h-32 md:w-36 md:h-36">
        <h2 class="text-sm sm:text-xl mt-2 font-bold">{{ profile.name }}</h2>
        <p class="text-sm sm:text-xl mt-2 italic">{{ profile.roles }}</p>
        <a :href="'mailto:' + profile.email" class="text-xs sm:text-lg mt-2 text-wrap break-words max-w-full line-clamp-2">{{ profile.email }}</a>
        <p class="text-xs sm:text-lg  mt-2 mb-4">{{ profile.phone }}</p>
    </div>
</div>
</template>

<script setup>
const profiles = ref([]);
async function getStaff() {
  const query = await queryContent("/staff").sort({ roles: 1 }).find();
  profiles.value = query;
}

onMounted(() => {
  getStaff();
});

</script>
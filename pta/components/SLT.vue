<template>
    <div class="flex flex-wrap px-2">
        <div v-for="(profile, index) in profiles" :key="index" id="profile"
            class="content-center w-1/2 2xl:w-1/3 my-4 flex items-center text-center text-wrap flex-col">
            <img :src=profile.image :alt="profile.name" class="rounded-full w-24 h-24 sm:w-32 sm:h-32 md:w-36 md:h-36">
            <h2 class="text-sm sm:text-xl mt-2 font-bold">{{ profile.name }}</h2>
            <a :href="'mailto:' + profile.email" class="text-xs sm:text-lg mt-2 text-wrap break-words max-w-full line-clamp-2">{{ profile.email }}</a>
        </div>
    </div>
</template>

<script setup>
const profiles = ref([]);
async function getSLT() {
    const query = await queryContent("/slt").find();
    profiles.value = query;
}
onMounted(() => {
    getSLT();
});  
</script>
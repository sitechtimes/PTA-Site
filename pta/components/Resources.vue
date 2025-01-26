<template>
  <div class="md:mx-6">
    <h2 class="text-xl mt-6 mb-2 md:text-2xl lg:text-4xl font-bold">RESOURCES</h2>
    <div class="grid lg:grid-cols-2 grid-rows-2 gap-5">
      <div v-for="resource in resources" :key="resource.title"
        class="bg-white rounded-xl w-full h-full mb-2 flex flex-row border border-[#4c4038a6]">
        <img :src="resource.img" class="p-4 w-1/2 row-span-3 self-center md:w-1/3 lg:w-1/4 object-contain">
        <div class="flex flex-col p-4">
          <h3 class="font-bold text-2xl">{{ resource.title }}</h3>
          <p class="text-lg">{{ resource.description }}</p>
          <a :href="resource.link" target="_blank" rel="noopener noreferrer"
            class="bg-[#C9B23A] rounded-lg px-4 py-2 w-fit text-center font-semibold text-white transition duration-150 ease-out hover:ease-in hover:opacity-50 my-8 text-xl">
            Read More
          </a>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>
const resources = [
  {
    img: "/resources/NEWSITHSLogo.png",
    title: "Automated Telephone Message Directory",
    description: "Contact Staten Island Technical High School.",
    link: "https://www.siths.org/apps/pages/index.jsp?uREC_ID=1555040&type=d&pREC_ID=1680913"
  },
  {
    img: "/resources/NavianceLogo.png",
    title: "Naviance",
    description: "Track secondary goals and success",
    link: "https://id.naviance.com/"
  },
  {
    img: "/resources/NycDoeLogo.png",
    title: "NYCDOE Websites",
    description: "Keep track of student documents and official city calendars",
    link: "https://www.schools.nyc.gov/"
  },
  {
    img: "/logo/ptaLogo.png",
    title: "SITHS PTA By-Laws",
    description: "Read more about the PTA",
    link: "https://docs.google.com/document/d/1gNyKPMDOUxeW2AadJFuOXtla3jd_bzjw/edit?usp=sharing&ouid=109431569121511580485&rtpof=true&sd=true"
  }
]
</script>

<style scoped></style>
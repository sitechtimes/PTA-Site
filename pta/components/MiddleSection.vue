<template>
  <div class="flex flex-col px-10 gap-y-10 lg:px-20">
    <!-- about us section -->
    <section id="aboutUs lg:mt-6">
      <div class="text-left">
        <h2 class="subh ">ABOUT US</h2>
        <p class="text paragraph">
          The mission of Staten Island Tech’s PTA is to support our school through advocacy, volunteerism and fundraising.
          From our bake sales to our annual Spring Gala, we work diligently to raise money in order to financially support
          our school’s needs such as online and software services, facility upgrades and social events / celebrations.
        </p>
        <p class="text paragraph">
          While Staten Island Tech provides a strong academic environment for our children, the school cannot do this
          alone. Participating with the PTA is vital to our students and school community. Please join our meeting each
          month to learn about the ongoing activities and events that help make our school a success. Also,
          <b>
            please support our school with our suggested donations towards PTA dues. No amount is too small or too
            great
          </b>.
        </p>
      </div>
    </section>

    <!-- activities section -->
    <section id="activities" class="flex flex-col justify-between items-start gap-10 xl:mt-6 lg:flex-row">
  <div class="information">
    <h2 class="subh mb-4">ACTIVITIES</h2>
    <p class="text">
      The SITHS PTA is a group of parents and faculty/staff members who work together to provide our children with
      resources and activities to make their school experience the best ever!
    </p>
  </div>
  <div id="gallery" class="w-full">
    <Gallery />
  </div>
</section>

  </div>
</template>

<script setup>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
import { onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  gsap.from("#aboutUs", {
    x: 100,
    opacity: 1,
    duration: 2,
    scrollTrigger: {
      trigger: "#aboutUs",
      start: "top 80%",
      end: "top 50%",
      scrub: 1,
      once: true,
    },
  });

  gsap.from("#activities", {
    x: 100,
    opacity: 0,
    duration: 2,
    scrollTrigger: {
      trigger: "#activities",
      start: "top 80%",
      end: "top 50%",
      scrub: 1,
      once: true,
    },
  });
});
</script>

<!-- <style scoped>
/* .information {
  margin-left: 5%;
} */
@import "../assets/base.css";

.subh {
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
}

#minutes {
  margin-top: 0rem;
  margin-bottom: 10rem;
}

.linkCon {
  text-decoration-color: var(--text-color);
  display: flex;
  flex-direction: row;
}

img {
  margin-right: 0.5rem;
  vertical-align: middle;
  width: 1.5vw;
  fill: var(--text-color);
  height: 1.5vw;
  margin-bottom: 0.4vw;
}

#section__MiddleSection {
  display: flex;
  flex-direction: row;
  gap: 5vw;
  justify-content: space-between;
  width: 84vw;
  margin: 0 auto;
  margin-top: 5rem;
}

.information {
  display: flex;
  flex-direction: column;
  width: 50%;
  z-index: 2;
}

#gallery {
  display: flex;
  flex-direction: column;
  width: 50vw;
  justify-content: center;
  margin-bottom: 5vw;
}

@media only screen and (max-width: 1024px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2vh;
    /* margin-top: 20rem; */
  }

  #gallery {
    margin-right: 0;
  }

  #minutes {
    margin-bottom: 0rem;
  }

  .information,
  #activites {
    display: flex;
    justify-content: center;
    width: 100%;
  }

  p,
  h2,
  h3 {
    width: 100%;
    text-align: center;
  }

  p {
    font-size: 2vw;
  }
}

@media only screen and (max-width: 992px) {
  img {
    width: 2vw;
    height: 2vw;
  }

  #section__MiddleSection {
    margin-top: 2rem;
  }

  #gallery {
    display: flex;
    justify-content: center;
    width: 60vw;
  }
}

@media only screen and (max-width: 850px) {
  p {
    font-size: 3vw;
  }

  /* #section__MiddleSection {
    margin-top: 14rem;
  } */
}

@media screen and (max-width: 768px) {
  #gallery {
    width: 60vw;
  }
}

@media only screen and (max-width: 576px) {
  #minutes {
    padding-bottom: 1rem;
  }

  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    max-width: 90vw;
    width: 100%;
    /* margin-top: 21rem; */
  }

  .information,
  #activites {
    display: flex;
    justify-content: center;
  }

  p,
  h2,
  h3 {
    width: 100%;
    text-align: center;
  }

  img {
    width: 3vw;
    height: 3vw;
  }

  #gallery {
    width: 70vw;
  }
}

.text {
  margin-top: 0;
}

.subh {
  margin-bottom: 0rem;
  margin-top: 1rem;
}

@media only screen and (max-width: 450px) {
  #gallery {
    width: 80vw;
  }

  /* #section__MiddleSection {
    margin-top: 28rem;
  } */
}

@media only screen and (max-width: 356px) {
  img {
    width: 4vw;
    height: 4vw;
  }

  /* #section__MiddleSection {
    margin-top: 40rem;
  } */
}

@media only screen and (max-width: 248px) {
  /* #section__MiddleSection {
    margin-top: 50rem;
  } */
}
</style> -->

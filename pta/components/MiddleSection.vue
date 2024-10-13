<template>
  <div>
    <section id="section__MiddleSection">
      <div class="information">
        <div id="activities">
          <h2 ref="activities" class="subh">ACTIVITIES</h2>
          <p ref="activitiesDesc" class="text">
            The SITHS PTA is a group of parents and faculty/staff members who work together to provide our children with
            resources and activities to make their school experience the best ever!
          </p>
        </div>
      </div>
      <div ref="gallery" id="gallery">
        <Gallery />
      </div>
    </section>
  </div>
</template>

<script setup>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

const minutes = ref([]);
const recordings = ref([]);

function scrollActivities() {
  gsap.to({
    ScrollTrigger: {
      trigger: ".activities",
      start: "center center",
      end: "bottom top",
    },
  });
}

async function getMinutes() {
  const query = await queryContent("/minutes").find();
  minutes.value = query.slice(1).slice(-3);
}

async function getRecordings() {
  const query = await queryContent("/recordings").find();
  recordings.value = query.slice(1).slice(-3);
}

// #minutes and #recordings don't exist...

// onMounted(async () => {
//   await getMinutes();
//   gsap.from("#activities", {
//     scrollTrigger: "#activities",
//     delay: 0.6,
//     duration: 1,
//     x: 0,
//     opacity: 100,
//   });

//   gsap.from("#minutes", {
//     scrollTrigger: "#minutes",
//     delay: 0.6,
//     duration: 1,
//     x: -600,
//     opacity: 0,
//   });

//   await getRecordings();
//   gsap.from("#activities", {
//     scrollTrigger: "#activities",
//     delay: 0.6,
//     duration: 1,
//     x: -600,
//     opacity: 0,
//   });
//   gsap.from("#recordings", {
//     scrollTrigger: "#recordings",
//     delay: 0.6,
//     duration: 1,
//     x: -600,
//     opacity: 0,
//   });
//   gsap.from("#gallery", {
//     scrollTrigger: "#gallery",
//     delay: 0.6,
//     duration: 1,
//     x: -600,
//     opacity: 0,
//   });
// });
</script>

<style scoped>
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
</style>

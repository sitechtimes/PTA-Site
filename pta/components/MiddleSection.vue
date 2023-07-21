<template>
  <section id="section__MiddleSection">
    <div class="information">
      <div id="activities">
        <h2 ref="activities">ACTIVITIES</h2>
        <p ref="activitiesDesc">
          The SITHS PTA is a group of parents and faculty/staff members who work
          together to provide our children with resources and activities to make
          their school experience the best ever!
        </p>
      </div>
      <div ref="minutes" id="minutes">
        <h2>MEETING MINUTES</h2>
        <a href="" ref="minutesLink" target="_blank" rel="noopener">
          <h3>Link to May 2023 Meeting Minutes</h3>
        </a>
      </div>
    </div>
    <div ref="gallery" id="gallery">
      <PhotoGallery />
    </div>
  </section>
</template>

<script>
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    // const { activities } = this.$refs;
    // const { activitiesDesc } = this.$refs;
    // const { minutes } = this.$refs;
    // const { minutesLink } = this.$refs;
    // const { gallery } = this.$refs;
    // const timeline = gsap.timeline();
    console.log("mount");
    gsap.from("#activities", {
      scrollTrigger: "#activities",
      duration: 2,
      x: -600,
      opacity: 0,
    });
    gsap.from("#minutes", {
      scrollTrigger: "#minutes",
      duration: 2,
      x: -600,
      opacity: 0,
    });
    gsap.from("#gallery", {
      scrollTrigger: "#gallery",
      duration: 2,
      x: -600,
      opacity: 0,
    });
  },
  data() {
    return {};
  },
  methods: {
    scrollActivities() {
      gsap.to({
        ScrollTrigger: {
          trigger: ".activities",
          start: "center center",
          end: "bottom top",
        },
      });
    },
  },
};
/* this.home.addEventListener("mouseenter", () => animation.play());
this.home.addEventListener("mouseleave", () => animation.reverse()); */
</script>
<style scoped>
/* .information {
  margin-left: 5%;
} */

h2 {
  font-weight: bold;
  font-family: "Kumbh Sans", sans-serif;
}

p,
a {
  font-weight: 500;
  width: 80%;
  font-family: "Karla", sans-serif;
}

#minutes {
  margin-top: 4rem;
}

#section__MiddleSection {
  margin-top: 1rem;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
  justify-content: center;
  margin-left: 5%;
}

.information {
  display: flex;
  flex-direction: column;
  width: 50vw;
  z-index: 2;
}

#gallery {
  display: flex;
  width: 50vw;
  justify-content: center;
}

@media screen and (max-width: 576px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 0;
  }

  .information {
    width: 100%;
    padding-left: 2rem;
  }

  .gallery {
    width: 90vw;
  }
}

@media screen and (max-width: 1024px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 0;
  }

  .information {
    width: 90%;
  }
}
</style>

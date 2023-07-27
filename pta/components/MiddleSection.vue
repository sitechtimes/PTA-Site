<template>
  <section id="section__MiddleSection">
    <div class="information">
      <div id="activities">
        <h2 ref="activities" class="subh">ACTIVITIES</h2>
        <p ref="activitiesDesc" class="text">
          The SITHS PTA is a group of parents and faculty/staff members who work
          together to provide our children with resources and activities to make
          their school experience the best ever!
        </p>
      </div>
      <div ref="minutes" id="minutes">
        <h2 class="subh">MEETING MINUTES</h2>
        <div>
          <a
            href=""
            class="linkCon"
            ref="minutesLink"
            target="_blank"
            rel="noopener"
          >
            <h3 class="text">
              <img
                id="linkIcon"
                src="../components/icons/link.svg"
                alt="link icon"
              />Link to May 2023 Meeting Minutes
            </h3>
          </a>
        </div>
      </div>
    </div>
    <div ref="gallery" id="gallery">
      <PhotoGallery />
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap/dist/gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

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
      delay: 0.2,
      duration: 1,
      x: -600,
      opacity: 0,
    });
    gsap.from("#minutes", {
      scrollTrigger: "#minutes",
      delay: 0.2,
      duration: 1,
      x: -600,
      opacity: 0,
    });
    gsap.from("#gallery", {
      scrollTrigger: "#gallery",
      delay: 0.2,
      duration: 1,
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
@import "../assets/base.css";
.subh {
  margin-bottom: 1.5rem;
}
#minutes {
  margin-top: 4rem;
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
  p {
    font-size: 2vw;
  }
}
@media screen and (max-width: 850px) {
  p {
    font-size: 3vw;
  }
}
</style>

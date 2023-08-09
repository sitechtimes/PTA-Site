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
        <div v-for="minute in minutes">
          <a
            :href="minute.link"
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
              />{{ minute.title }}
            </h3>
          </a>
        </div>
      </div>
    </div>
    <div ref="gallery" id="gallery">
      <Gallery />
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap/dist/gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
  data() {
    return {
      minutes: Array,
    };
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
    async getMinutes() {
      const query = queryContent("/minutes").sort().limit(2).find();
      console.log(query);
      query.then((response) => {
        this.minutes = response;
      });
    },
  },
  mounted() {
    this.getMinutes();
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
  margin-top: 2rem;
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
  margin-top: 1rem;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
  justify-content: center;
}

.information {
  display: flex;
  flex-direction: column;
  width: 50vw;
  z-index: 2;
  margin-left: 6.5vw;
  margin-right: 5vw;
}

#gallery {
  display: flex;
  width: 50vw;
  justify-content: center;
  margin-right: 6.5rem;
  margin-bottom: 5vw;
}

@media only screen and (max-width: 1024px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 0;
  }

  .information {
    width: 80%;
    margin-right: 6.5vw;
  }
  #gallery {
    margin-right: 0;
    margin-top: 3vw;
    width: 100vw;
  }
  #minutes {
    margin-bottom: 0rem;
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
  p {
    font-size: 2vw;
  }
}
@media only screen and (max-width: 992px) {
  img {
    width: 2vw;
    height: 2vw;
  }
}
@media only screen and (max-width: 850px) {
  p {
    font-size: 3vw;
  }
}
@media only screen and (max-width: 576px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 0;
  }

  .information {
    width: 80%;
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
}
@media only screen and (max-width: 450px) {
  #gallery {
    width: 80vw;
  }
}
@media only screen and (max-width: 356px) {
  img {
    width: 4vw;
    height: 4vw;
  }
}
</style>

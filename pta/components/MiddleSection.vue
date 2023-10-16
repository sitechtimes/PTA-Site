<template>
  <section id="section__MiddleSection">
    <div class="aboutUs">
      <h3 class="subh">ABOUT US</h3>
      <p class="text paragraph">
        The mission of Staten Island Tech’s PTA is to support our school through
        advocacy, volunteerism and fundraising. From our bake sales to our
        annual Spring Gala, we work diligently to raise money in order to
        financially support our school’s needs such as online and software
        services, facility upgrades and social events / celebrations.
      </p>
      <p class="text paragraph">
        While Staten Island Tech provides a strong academic environment for our
        children, the school cannot do this alone. Participating with the PTA is
        vital to our students and school community. Please join our meeting each
        month to learn about the ongoing activities and events that help make
        our school a success. Also,<b>
          please support our school with our suggested donations towards PTA
          dues. No amount is too small or too great</b
        >.
      </p>
    </div>
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
      const query = queryContent("/minutes").find();
      console.log(query);

      query.then((response) => {
        console.log(response.slice(1).slice(-3), response.length);
        this.minutes = response.slice(1).slice(-3);
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
  margin-top: 13rem;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
  justify-content: center;
}

.paragraph {
  margin-bottom: 1.5vw;
}

.aboutUs {
  width: 83vw;
  display: flex;
  flex-direction: column;
  margin-left: 7vw;
  margin-top: 15vw;
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
@media only screen and (max-width: 1600px) {
  #section__MiddleSection {
    margin-top: 14rem;
  }

  .aboutUs {
    width: 80vw;
    margin-top: 12vw;
  }
}
@media only screen and (max-width: 1400px) {
  #section__MiddleSection {
    margin-top: 22rem;
  }
}
@media only screen and (max-width: 1200px) {
  #section__MiddleSection {
    margin-top: 20rem;
  }
  .aboutUs {
    margin-left: 8vw;
    margin-top: 7vw;
    width: 85vw;
  }
}
@media only screen and (max-width: 1024px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 20rem;
  }
  .aboutUs {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: left;
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
  #section__MiddleSection {
    margin-top: 13rem;
  }
  .aboutUs {
    margin-top: -18vw;
  }
}
@media only screen and (max-width: 850px) {
  p {
    font-size: 3vw;
  }
  #section__MiddleSection {
    margin-top: 14rem;
  }
}
@media screen and (max-width: 768px) {
  .aboutUs {
    margin-top: -20vw;
    margin-left: 9vw;
  }
}
@media only screen and (max-width: 576px) {
  #section__MiddleSection {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 21rem;
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
  .aboutUs {
    margin-top: 8rem;
    margin-left: 12vw;
    width: 75vw;
  }
}

@media only screen and (max-width: 450px) {
  #gallery {
    width: 80vw;
  }
  #section__MiddleSection {
    margin-top: 28rem;
  }
  .aboutUs {
    margin-top: 10rem;
  }
}

@media only screen and (max-width: 356px) {
  img {
    width: 4vw;
    height: 4vw;
  }
  #section__MiddleSection {
    margin-top: 40rem;
  }
  .aboutUs {
    margin-left: 14vw;
    margin-top: 55vw;
  }
}
@media only screen and (max-width: 248px) {
  #section__MiddleSection {
    margin-top: 50rem;
  }
}
</style>

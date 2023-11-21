<template>
  <section id="section_AboutUs">
    <div ref="aboutUs" id="aboutUs" class="aboutUs">
      <h3 id="subh" class="subh">ABOUT US</h3>
      <p id="paragraph" class="text paragraph">
        The mission of Staten Island Tech’s PTA is to support our school through
        advocacy, volunteerism and fundraising. From our bake sales to our
        annual Spring Gala, we work diligently to raise money in order to
        financially support our school’s needs such as online and software
        services, facility upgrades and social events / celebrations.
      </p>
      <p id="paragraph" class="text paragraph">
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
  </section>
</template>


<script>
import { gsap } from "gsap/dist/gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
  data() {},
  methods: {
    scrollActivities() {
      gsap.to({
        ScrollTrigger: {
          trigger: "#aboutUs",
          start: "center center",
          end: "bottom top",
        },
      });
    },
    
  },
  mounted() {
    gsap.from("#subh", {
      scrollTrigger: "#subh",
      delay: 0.2,
      duration: 1,
      x: -600,
      opacity: 0,
    });
    gsap.from("#paragraph", {
      scrollTrigger: "#paragraph",
      delay: 0.4,
      duration: 1,
      x: -600,
      opacity: 0,
    });
  },

};
</script>

<style scoped>
@import "../assets/base.css";
.paragraph {
  margin-bottom: 1.5vw;
}

.aboutUs {
  width: 83vw;
  display: flex;
  flex-direction: column;
  margin-left: 6.5vw;
}

@media only screen and (max-width: 1200px) {
  .aboutUs {
    margin-left: 8vw;
    width: 85vw;
  }
}
@media only screen and (max-width: 576px) {
  .aboutUs {
    width: 75vw;
    margin-left: 12%;
  }
}
/* @media only screen and (max-width: 1600px) {
  .aboutUs {
    width: 80vw;
    margin-top: 12vw;
  }
}
@media only screen and (max-width: 1400px) {
}
@media only screen and (max-width: 1200px) {
  .aboutUs {
    margin-left: 8vw;
    margin-top: 7vw;
    width: 85vw;
  }
}
@media only screen and (max-width: 1024px) {
  .aboutUs {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: left;
  }
}
@media only screen and (max-width: 992px) {
  .aboutUs {
    margin-top: -18vw;
  }
}
@media only screen and (max-width: 850px) {
}
@media screen and (max-width: 768px) {
  .aboutUs {
    margin-top: -20vw;
    margin-left: 9vw;
  }
}

@media only screen and (max-width: 450px) {
  .aboutUs {
    margin-top: 10rem;
  }
}

@media only screen and (max-width: 356px) {
  .aboutUs {
    margin-left: 14vw;
    margin-top: 55vw;
  }
}
@media only screen and (max-width: 248px) {
  #section__MiddleSection {
    margin-top: 50rem;
  }
} */
</style>

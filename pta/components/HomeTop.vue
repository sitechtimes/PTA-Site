<template>
  <div ref="home" class="home" id="homeTopCon">
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <div id="homeTopText">
      <h2 id="pta" ref="pta">Parent Teacher Association @</h2>
      <h1 id="siths" ref="siths">
        <div ref="statenIsland">STATEN ISLAND</div>
        <div ref="technical">TECHNICAL</div>
        <div ref="highSchool">HIGH SCHOOL</div>
      </h1>
      <p id="address" ref="address">
        485 Clawson Street, Staten Island, NY 10306
      </p>
    </div>
    <div class="events">
      <UpcomingEvents />
    </div>
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
  </div>
</template>
<script>
import gsap from "gsap";
export default {
  mounted() {
    const { statenIsland } = this.$refs;
    const { technical } = this.$refs;
    const { highSchool } = this.$refs;
    const { pta } = this.$refs;
    const { address } = this.$refs;
    const timeline = gsap.timeline();
    timeline
      .from(pta, { duration: 1.5, x: -1000 })
      .from(statenIsland, 1.5, { x: -1000 }, "<0.5")
      .from(technical, 1.5, { x: -1000 }, "<0.1")
      .from(highSchool, 1.5, { x: -1000 }, "<0.1")
      .from(address, { duration: 1, x: -1000 }, "<0.4");
  },
  data() {
    return {};
  },
  methods: {},
};
/* this.home.addEventListener("mouseenter", () => animation.play());
this.home.addEventListener("mouseleave", () => animation.reverse()); */
</script>

<style scoped>
@import "../assets/base.css";
.arrow {
  border: solid rgb(0, 0, 0);
  border-width: 0 4px 4px 0;
  display: inline-block;
  padding: 20px;
  transform: rotate(45deg);
  -webkit-transform: rotate(45deg);
  position: relative;
  z-index: 5;
  transition: 0.3s;
  border-radius: 3px;
  opacity: 50%;
}
.arrow:hover {
  opacity: 100%;
}

.arrowContainer {
  position: absolute;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  bottom: 40%;
}
.aboutUs {
  width: 83vw;
  display: flex;
  flex-direction: column;
  margin-left: 7vw;
  margin-top: 15vw;
}
.events {
  position: relative;
  left: 57%;
  top: 17%;
  width: 37vw;
}
.paragraph {
  margin-bottom: 1.5vw;
}

@media screen and (max-width: 1600px) {
  .aboutUs {
    margin-top: 12vw;
  }
}
@media screen and (max-width: 1600px) {
  .aboutUs {
    width: 80vw;
  }
  p {
    font-size: 16px;
  }
}
@media screen and (max-width: 1200px) {
  .aboutUs {
    margin-left: 8vw;
    margin-top: 7vw;
    width: 85vw;
  }
  p {
    font-size: 16px;
  }
  .events {
    margin: 0;
    display: flex;
    justify-content: center;
    position: relative;
    left: 65%;
    top: 12%;
    width: 20vw;
  }
}
@media screen and (max-width: 1024px) {
  .aboutUs {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: left;
  }
}
@media screen and (max-width: 992px) {
  .aboutUs {
    margin-top: -18vw;
  }
  .events {
    position: relative;
    left: 56%;
    top: 0%;
    width: 35vw;
  }
}
@media only screen and (max-width: 992px) and (orientation: portrait) {
  #homeTopText {
    top: 3%;
  }
}
@media screen and (max-width: 768px) {
  p {
    font-size: 14px;
  }

  h3 {
    font-size: 17px;
  }
  .aboutUs {
    margin-top: -20vw;
    margin-left: 9vw;
  }
}
@media screen and (max-width: 768px) and (orientation: landscape) {
  #homeTopText {
    transform: translate(-50%, 1vw);
  }
}

@media screen and (max-width: 576px) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    margin-top: 5%;
    left: 45%;
    transform: translate(-50%, 18vw);
    white-space: nowrap;
    text-align: left;
  }
  #address {
    margin: 0%;
    font-weight: 500;
    letter-spacing: 0.047vw;
    font-size: 3.2vw;
  }
  #siths {
    margin: 0%;
    font-size: 8vw;
    font-weight: 800;
    letter-spacing: 0.12rem;
    margin-bottom: 3vw;
  }
  #pta {
    margin: 0%;
    font-size: 4vw;
    font-weight: 400;
    letter-spacing: 0.047vw;
    margin-bottom: 3vw;
  }
  .events {
    margin: 0;
    margin-top: 35vw;
    display: flex;
    justify-content: center;
    left: 0%;
    width: 100%;
  }
  .aboutUs {
    margin-top: 8rem;
    margin-left: 12vw;
    width: 75vw;
  }
}
@media only screen and (max-width: 450px) {
  .aboutUs {
    margin-top: 10rem;
  }
  #homeTopText {
    top: 6%;
    left: 47.4%;
  }
  p {
    font-size: 3.5vw;
  }
  h3 {
    font-size: 20px;
  }
}
@media only screen and (max-width: 356px) {
  #homeTopText {
    top: 8%;
    left: 50%;
  }
  p {
    font-size: 4.72vw;
  }
  .aboutUs {
    margin-left: 14vw;
    margin-top: 55vw;
  }
}
@media only screen and (max-width: 280px) and (orientation: portrait) {
  p {
    font-size: 4.72vw;
  }
  .aboutUs {
    margin-left: 14vw;
    margin-top: 15rem;
  }
}
@media only screen and (max-width: 220px) and (orientation: portrait) {
  p {
    font-size: 5.3vw;
  }
}
@media screen and (min-width: 576px) {
  #homeTopCon {
    background: var(--bg-gradient);
    width: 100%;
    height: 220vw;
    margin: 0;

    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    left: 50%;
    transform: translate(-50%, 18vw);
    white-space: nowrap;
    text-align: left;
  }
  #address {
    margin: 0%;
    font-weight: 500;
    letter-spacing: 0.047vw;
    font-size: 3.7vw;
  }
  #siths {
    margin: 0%;
    font-size: 9.2vw;
    font-weight: 800;
    letter-spacing: 0.12rem;
    margin-bottom: 3.5vw;
  }
  #pta {
    margin: 0%;
    font-size: 4.4vw;
    font-weight: 400;
    letter-spacing: 0.047vw;
    margin-bottom: 3vw;
  }
}
@media screen and (min-width: 576px) {
  #homeTopCon {
    background: var(--bg-gradient);
    width: 100vw;
    height: 70vw;
    margin: 0;

    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    top: 8%;
    left: 30%;
    white-space: nowrap;
    text-align: left;
  }
  #address {
    margin: 0%;
    font-weight: 500;
    letter-spacing: 0.047vw;
    font-size: 1.97vw;
  }
  #siths {
    margin: 0%;
    font-size: 4.4vw;
    font-weight: 800;
    letter-spacing: 0.12rem;
    margin-bottom: 1vw;
  }
  #pta {
    margin: 0%;
    font-size: 2.2vw;
    font-weight: 400;
    letter-spacing: 0.047vw;
    margin-bottom: 1vw;
  }
}
@media screen and (min-width: 768px) {
  #homeTopCon {
    background: var(--bg-gradient);
    width: 100%;
    height: 60vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
  }
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    transform: translate(0%, 0vw);
    top: 30%;
    left: 8vw;
    text-align: left;
  }
  #address {
    margin: 0%;
    font-weight: 400;
    letter-spacing: 0.48px;
    font-size: 1.7vw;
  }
  #siths {
    margin: 0%;
    font-size: 5vw;
    font-weight: 800;
    letter-spacing: 0.12rem;
    margin-bottom: 0.2vw;
  }
  #pta {
    margin: 0%;
    font-size: 2vw;
    font-weight: 400;
    letter-spacing: 0.48px;
    margin-bottom: 0.7vw;
  }
}
@media screen and (min-width: 1200px) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    text-align: left;
    position: absolute;
    transform: translate(0%, 0vw);
    top: 26%;
    left: 7vw;
  }
  #address {
    margin: 0%;
    font-weight: 400;
    letter-spacing: 0.48px;
    font-size: 1.27vw;
  }
  #siths {
    margin: 0%;
    font-size: 5vw;
    font-weight: 800;
    line-height: 129.164%;
    letter-spacing: 0.12rem;
    margin-bottom: 0.2vw;
  }
  #pta {
    margin: 0%;
    font-size: 2.1vw;
    font-weight: 400;
    letter-spacing: 0.48px;
    margin-bottom: 0.4vw;
  }
}
@media screen and (min-width: 1400px) {
  #homeTopText {
    top: 22%;
  }
}
</style>

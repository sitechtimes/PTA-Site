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

.events {
  position: relative;
  left: 57%;
  top: 17%;
  width: 37vw;
}

@media screen and (max-width: 1200px) {
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
@media screen and (max-width: 992px) {
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
}
@media only screen and (max-width: 450px) {
  #homeTopText {
    top: 6%;
    left: 47.4%;
  }
}
@media only screen and (max-width: 356px) {
  #homeTopText {
    top: 8%;
    left: 50%;
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

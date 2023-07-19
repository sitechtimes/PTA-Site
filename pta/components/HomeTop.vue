<template>
  <div ref="home" class="home" id="homeTopCon">
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <div id="homeTopText">
      <h2 id="pta" ref="pta">Parent Teacher Association @</h2>
      <h1 id="siths" ref="siths">
        STATEN ISLAND <br />TECHNICAL <br />HIGH SCHOOL
      </h1>
      <p id="address" ref="address">
        485 Clawson Street, Staten Island, NY 10306
      </p>
    </div>
  </div>
</template>
<script>
import gsap from "gsap";
export default {
  mounted() {
    const { home } = this.$refs;
    const { pta } = this.$refs;
    const { siths } = this.$refs;
    const { address } = this.$refs;
    const timeline = gsap.timeline();
    timeline
      .from(pta, { x: -1000 })
      .from(siths, { stagger: 5, x: -1000 })
      .from(address, { x: -1000 });
  },
};
/* this.home.addEventListener("mouseenter", () => animation.play());
this.home.addEventListener("mouseleave", () => animation.reverse()); */
</script>

<style scoped>
@import "../assets/base.css";
@media screen and (max-width: 576px) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    top: 5%;
    left: 45%;
    transform: translate(-50%, 34vw);
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
}

@media screen and (min-width: 576px) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    left: 50%;
    transform: translate(-50%, 34vw);
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

@media screen and (min-width: 576px) and (orientation: landscape) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    top: -14%;
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
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    left: 50%;
    transform: translate(-50%, 30vw);
    text-align: left;
  }
  #address {
    margin: 0%;
    font-weight: 400;
    letter-spacing: 0.047vw;
    font-size: 3.27vw;
  }
  #siths {
    margin: 0%;
    font-size: 9vw;
    font-weight: 800;
    letter-spacing: 0.12rem;
    margin-bottom: 0.5vw;
  }
  #pta {
    margin: 0%;
    font-size: 4.1vw;
    font-weight: 400;
    letter-spacing: 0.047vw;
    margin-bottom: 1.3vw;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
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

@media screen and (min-width: 992px) {
  #homeTopText {
    color: var(--text-color);
    font-family: var(--font-heading);
    position: absolute;
    transform: translate(0%, 0vw);
    top: 28%;
    left: 7vw;
    text-align: left;
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

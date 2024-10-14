<template>
  <div class="flex flex-col lg:flex-row w-screen lg:justify-between lg:px-20 lg:items-center ">
    <div class="ml-10 flex flex-col justify-center items-left w-screen h-fit py-10 lg:w-[45vw] lg:h-screen lg:gap-y-6">
      <h2 id="pta" ref="pta" class="text-3xl lg:text-3xl w-fit">Parent Teacher Association @</h2>
      <h1 ref="schoolName" class="text-5xl font-bold mr-20 leading-snug sm:text-5xl md:text-6xl lg:w-fit lg:text-8xl lg:leading-normal">
        STATEN ISLAND <br> TECHNICAL <br> HIGH SCHOOL
      </h1>
      <p id="address" ref="address" class="text-3xl lg:text-3xl mt-4">
        485 Clawson Street, Staten Island, NY 10306
      </p>
    </div>
    <div class="flex w-full lg:w-1/2">
      <EventsComponent />
    </div>
  </div>
</template>


<script setup>
import gsap from "gsap";
const schoolName = ref();
const pta = ref();
const address = ref();


onMounted(() => {
  const tl = gsap.timeline();
  tl
    .from(pta.value, { duration: 1.5, x: -1000 })
    .from(schoolName.value, { duration: 1.5, x: -1000 }, "<0.5") // animate entire school name
    .from(address.value, { duration: 1, x: -1000 }, "<0.4");
});

/* this.home.addEventListener("mouseenter", () => animation.play());
this.home.addEventListener("mouseleave", () => animation.reverse()); */
</script>

<style scoped>
@import "../assets/base.css";

#home {
  display: flex;
  flex: row;
  justify-content: space-between;
  align-items: center;
}

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
  width: 37vw;
}

#siths {
  display: flex;
  flex-direction: column;
}

@media screen and (max-width: 1600px) {
  p {
    font-size: 16px;
  }
}

@media screen and (max-width: 1500px) {
  #homeTopText {
    margin-top: 5rem;
  }

  .events {
    margin-top: 5rem;
  }
}

@media screen and (max-width: 1200px) {
  p {
    font-size: 16px;
  }

  .events {
    margin: 0;
    display: flex;
    justify-content: center;
    position: relative;
    width: 20vw;
  }
}

@media screen and (max-width: 1024px) {}

@media screen and (max-width: 992px) {
  .events {
    position: relative;
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
    height: 49vw;
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
    height: 49vw;
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

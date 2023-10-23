<template>
  <div>
    <div id="gradient">
      <section class="topComponent">
        <div class="leftComponent">
          <h1 class="heading" ref="heading">Wall of Gratitude</h1>
          <div class="thanks">
            <h2>Thank You!</h2>
            <p>
              We would like to thank everyone who helped out Lorem ipsum dolor
              sit amet, consectetur adipiscing elit, sed do eiusmod tempor
              incididunt ut labore et dolore magna aliqua. Ut enim ad minim
              veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
              ex ea commodo consequat. Ut enim ad minim veniam, quis nostrud
              exercitation ullamco laboris nisi ut aliquip ex ea commodo
              consequat. Ut enim ad minim veniam, quis nostrud exercitation
              ullamco laboris nis
            </p>
          </div>
        </div>
        <div class="image"></div>
        <div class="archive">
          <h3>Archive</h3>
          <div class="years">
            <div class="year"><h4>2023</h4></div>
            <div class="year"><h4>2022</h4></div>
            <div class="year"><h4>2021</h4></div>
            <div class="year"><h4>2020</h4></div>
            <div class="year"><h4>2019</h4></div>
            <div class="year"><h4>2018</h4></div>
            <div class="year"><h4>2017</h4></div>
            <div class="year"><h4>2016</h4></div>
          </div>
        </div>
      </section>
      <section class="bottomComponent">
        <h5>― •2023• ―</h5>
        <div class="donationArray">
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
          <div class="donationComponent"></div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { heading } = this.$refs;
    gsap.from(heading, { delay: 0, duration: 1, y: 100, opacity: 0 });
  },
};
</script>
<style scoped>
#gradient {
  width: 100%;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: linear-gradient(
    180deg,
    #feb89a 0%,
    #fdd8b8 18%,
    #ffecc5 40%,
    #faf2e1 75%,
    #faf2e1 80%,
    #fff 95%
  );
  overflow-x: hidden;
}
.topComponent {
  display: flex;
  flex-direction: row;
  margin: 8% 0 0 8%;
}
.heading {
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  font-size: 6rem;
  color: #483221;
  width: 33rem;
}
.thanks {
  font-family: "Kumbh Sans", san serif;
  font-weight: 400;
  font-size: 1.4rem;
  color: #483221;
  width: 40rem;
}
.image {
  margin: 4% 0 0 5%;
  width: 500px;
  height: 500px;
  border-radius: 50%;
  background-image: url(https://cdnb.artstation.com/p/assets/images/images/052/438/797/large/paul-seagull-compositing-9.jpg?1659794101);
  background-repeat: no-repeat;
  background-size: cover;
}
.archive {
  margin: 4% 0 0 5%;
  width: 19rem;
  height: 33rem;
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  color: #483221;
  text-align: center;
  overflow-y: scroll;
}
.years {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.year {
  margin: 5px;
  width: 16rem;
  height: 4rem;
  background-color: #fcf6e9;
  border-radius: 20px;
}
h3 {
  font-size: 3rem;
  margin: 1rem 0;
}
h4 {
  font-size: 1.4rem;
  margin: 7%;
}
.bottomComponent {
  font-family: "Kumbh Sans", san serif;
  margin-top: 5rem;
  color: #483221;
  text-align: center;
}
h5 {
  margin: auto;
  font-size: 3rem;
}
.donationArray {
  width: 90vw;
  margin: auto;
  display: flex;
  justify-content: space-evenly;
  text-align: center;
  flex-wrap: wrap;
  overflow-x: hidden;
}
.donationComponent {
  border-radius: 15px;
  border: #483221 solid 3px;
  width: 18rem;
  height: 21rem;
  margin: 15px 0;
}
</style>

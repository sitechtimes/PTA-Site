<template>
  <div>
    <div id="gradient"></div>
  <div id="popupscreen">
    <div id="outside" @click="TogglePopup()"></div>
    <div class="popup" ref="popup">
      <div class="popup-inner">
        <button class="popup-close" @click="TogglePopup()">✖</button>
        <h2 class="messageh">Message from the Parent Coordinator</h2>
        <h3 class="message">Welcome!

As you may know, in 2003 the Chancellor created the position of Parent Coordinator in all of the public schools in New York City. One of my roles is to be your parent advocate here at Tech and to actively facilitate a strong and productive relationship between the parents and school. Additionally, welcoming parents to a warm and friendly learning environment will provide an arena to share academic concerns related to your child's education.
Staying informed can help your family adjust to the high school experience. Many challenges take place during these four years and will no doubt impact your lives and influence behavior. The Tech family is here to assist you in any way possible. Please utilize the resources available to help you in the process.
As you come into the building I am making a point to greet you and check to see that your concerns are being addressed to your satisfaction. Please feel free to stop by and share what's on your mind. I look forward to meeting with you!
For the children,
</h3>
<h3 class="message">

Barbara Malenfant</h3>
<h3 class="c">“No Parent Left Behind”</h3>
<h3 class="c">718-667-3222 
</h3>
<h3 class="c">bmalenfant@schools.nyc.gov</h3>
      </div>
    </div>
  </div>
    <div>
      <h1 class="heading">CONTACTS</h1>
    </div>
    <div class="buttons">
      <button
        class="subtext"
        @click="(shownDiv = 'staff'), tester()"
        v-bind:style="{ backgroundColor: staffColor }"
        :class="{ shown: shownDiv === 'staff' }"
      >
        Staff
      </button>
      <button
        class="subtext"
        @click="(shownDiv = 'join'), tester()"
        v-bind:style="{ backgroundColor: joinColor }"
        :class="{ shown: shownDiv === 'join' }"
      >
        Join Us
      </button>
      <button
        class="subtext"
        @click="(shownDiv = 'sol'), tester()"
        v-bind:style="{ backgroundColor: solColor }"
        :class="{ shown: shownDiv === 'sol' }"
      >
        SLT
      </button>
    </div>
    <div v-if="shownDiv === 'staff'" class="container__box">
      <h1 class="subh">Board Members</h1>
      <div id="staff">
        <div class="staffCon" v-for="people in staff">
          <img class="staffPfp" :src="people.image" :alt="people.name" />
          <h3 class="subtext">{{ people.name }}</h3>
          <h4 class="subtext staffRole">{{ people.roles }}</h4>
          <a
            id="staffEmail"
            class="caption"
            :href="people.email"
            target="_blank"
            rel="noopener"
          >
            {{ people.email }}
          </a>
        </div>
      </div>
    </div>
    <div v-if="shownDiv === 'sol'" class="container__box">
      <h1 class="subh">School Leadership Team</h1>
      <div id="staff">
        <div class="staffCon" v-for="people in slt">
          <img class="staffPfp" :src="people.image" :alt="people.name" />
          <h3 class="subtext">{{ people.name }}</h3>
          <a
            class="caption"
            :href="people.email"
            target="_blank"
            rel="noopener"
          >
            {{ people.email }}
          </a>
        </div>
      </div>
    </div>
    <div>
      <div v-if="shownDiv === 'join'" class="container__box" id="join">
        <h1 class="subh">Join Us</h1>
        <div class="container__ParentVolunteer">
          <h2>PARENT VOLUNTEER OPPORTUNITIES</h2>
          <p>
            If you would like to volunteer at PTA events, please print out the
            attached volunteer form and submit to the PTA Room or email it to
            <a href="mailto:sitechpta@gmail.com" target="_blank" rel="noopener"
              >sitechpta@gmail.com</a
            >.
          </p>
          <p>Be part of the SI TECH PTA Grant Committee</p>
          <ul>
            <li>
              The grants committee researches and applies for grants to help
              fund school programs and activities including classroom/school
              upgrades, art, technology, maker-space, and the library. We reach
              out to foundations and corporations.
            </li>
            <li>
              Volunteers are needed to research grant opportunities or help
              write the grant proposals. No prior experience is necessary, time
              commitment is contingent on grant deadlines.
            </li>
            <li>
              Please email
              <a
                href="mailto:SITHSptagrantcommittee@gmail.com"
                target="_blank"
                rel="noopener"
                >SITHSptagrantcommittee@gmail.com</a
              >
              if interested.
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div id="footer">
      <NewFooter />
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
   props: ["TogglePopup"],
  mounted() {
    let tl = gsap.timeline();
    tl.from(".popup", { scale: 0.3, duration: 0.4 });
  },
  data() {
    return {
      staff: Array,
      shownDiv: "staff",
      joinColor: "transparent",
      staffColor: "#fcf6e9",
      solColor: "transparent",
      slt: Array,
    };
  },

  methods: {
    async getStaff() {
      const query = queryContent("/staff").sort({ roles: 1 }).find();
      console.log(query);
      query.then((response) => {
        this.staff = response;
      });
    },
    async getSLT() {
      const query = queryContent("/slt").find();
      console.log(query);
      query.then((response) => {
        console.log(response);
        this.slt = response;
      });
    },
    tester() {
      if (this.shownDiv === "join") {
        this.joinColor = "#fcf6e9";
        this.staffColor = "transparent";margin-le
        this.solColor = "transparent";
      } else if (this.shownDiv === "staff") {
        this.joinColor = "transparent";
        this.staffColor = "#fcf6e9";
        this.solColor = "transparent";
      } else {
        this.joinColor = "transparent";
        this.staffColor = "transparent";
        this.solColor = "#fcf6e9";
      }
    },
  },
  mounted() {
    gsap.from(".heading", { duration: 1, y: 100, opacity: 0 });
    gsap.from(".cal", 1, { x: 1000 }, "<0.5");

    this.getSLT();
    this.getStaff();
    gsap.from(".container__box", {
      duration: 0.5,
      y: 100,
      delay: 0.8,
      opacity: 0,
    });
    gsap.from(".buttons", {
      duration: 0.5,
      y: 100,
      delay: 0.5,
      opacity: 0,
    });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
.popup-inner{
  margin-left: 0;
}
.message{
  font-weight: lighter;
  font-size: 1.5rem;
  width: 95%;
    margin: 3% 0 0 0%;
}
.c{
  font-weight: lighter;
  font-size: 1.5rem;
  width: 90%;
    margin: 0% 0 0 0%;
}
.messageh{
      margin: 0% 0 0 0%;
}
#outside {
  background: transparent;
  height: 100vh;
  width: 100vw;
}
.popup-close {
  border: none;
  font-weight: bold;
  right: 1vw;
  background: transparent;
  position: fixed;
  top: 0%;
  font-size: 2vw;
  cursor: pointer;
}
#popupscreen {
  width: 100vw;
  height: auto;
  background-color: #0000003f;
  position: fixed;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  z-index: 99;
}
.popup {
  background: white;
  position: absolute;
  top: 50%;
  left: 50%;
  padding: 3rem;
  transform: translate(-50%, -50%);
  color: var(--text-color);
  font-family: var(--font-text);
  border-radius: 1.5vw;
  font-size: 1vw;
  width: 55vw;
}
button {
  transition: 0.3s;
}
button:hover {
  opacity: 0.7;
}

#join {
  padding-bottom: 10vw;
}
.heading {
  text-align: center;
  margin: 3% 0% 0% 0%;
}
.container__box {
  overflow-x: hidden;
  background-color: #fcf6e9;
  width: 65vw;
  margin-left: auto;
  margin-right: auto;
  margin-top: 2vw;
  padding: 3vw;
  padding-top: 4vw;
  border-radius: 1.5rem;
  color: #483221;
  font-family: var(--font-heading);
  margin-bottom: 10vw;
}
h1 {
  text-align: center;
  font-size: 2.5vw;
}
h2 {
  font-size: 2vw;
  margin-left: 5vw;
  margin-top: 2.5vw;
}

li,
p {
  font-size: 1.5vw;
  margin-left: 5vw;
  margin-right: 5vw;
}
p {
  margin-top: 2vw;
  margin-bottom: 2vw;
}
h3,
h4,
a {
  margin: 0;
  overflow-x: hidden;
}
.subh {
  margin-top: 0;
}
.staffCon {
  margin: 3vw;
  overflow-x: hidden;
  width: 15vw;
}
.subtext {
  font-weight: bolder;
}
.staffPfp {
  height: 10vw;
  width: 10vw;
  overflow-x: hidden;
  border-radius: 30vw;
}
#staff {
  display: flex;
  justify-content: center;
  text-align: center;
  flex-wrap: wrap;
  overflow-x: hidden;
}
.buttons {
  display: flex;
  justify-content: center;
  overflow-x: hidden;
}
#gradient {
  width: 100%;
  height: 80vw;
  position: absolute;
  top: 0;
  left: 0;
  padding: 0;
  background: var(--bg-gradient);
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
  align-items: center;
  overflow-x: hidden;
  z-index: -1;
  overflow-x: hidden;
}
.staffRole {
  font-weight: normal;
  font-size: 1.2vw;
}
#join {
  padding-bottom: 5.5vw;
  margin-bottom: 5vw;
}
h1 {
  text-align: center;
  font-size: 2.5vw;
  margin-top: 0;
}
h2 {
  font-size: 1.7vw;
}
h3,
h4,
a {
  margin: 0;
  overflow-x: shrink;
}
.staffCon {
  margin: 3vw;
  overflow-x: visible;
  width: 15vw;
}
.staffPfp {
  height: 10vw;
  width: 10vw;
  overflow-x: hidden;
  border-radius: 30vw;
}
#staff {
  display: flex;
  justify-content: space-evenly;
  text-align: center;
  flex-wrap: wrap;
  overflow-x: hidden;
}
.buttons {
  display: flex;
  justify-content: center;
  overflow-x: hidden;
}
button {
  padding: 1vw;
  padding-left: 2vw;
  padding-right: 2vw;
  margin-left: 2.5vw;
  margin-right: 2.5vw;
  margin-top: 1.5vw;
  width: 17vw;
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: auto;
  font-family: var(--font-heading);
  color: var(--text-color);
  border-radius: 1rem;
  border: none;
  transition: background-color 0.3s ease;
  background-color: #fcf6e9;
  cursor: pointer;
  overflow-x: hidden;
}
button:hover {
  background-color: #fde7cf;
}
@media only screen and (max-width: 1200px) {
  .staffRole {
    font-size: 1.5vw;
  }
  p {
    font-size: 2vw;
  }
  li {
    font-size: 2vw;
  }
}
@media only screen and (max-width: 1200px) {
  #gradient {
    height: 80vw;
  }
}
@media only screen and (max-width: 992px) {
  #gradient {
    height: 85vw;
  }
  button {
    border-radius: 0.8rem;
  }
  .staffCon {
    width: 40%;
  }
  .staffRole {
    font-size: 1.6vw;
  }
}
@media only screen and (max-width: 820px) {
  #gradient {
    height: 140vw;
  }
  h2 {
    font-size: 2.5vw;
    margin-left: 5vw;
    width: 60%;
    margin-top: 5vw;
  }
  h1 {
    font-size: 4vw;
    margin-top: 5vw;
  }
  li {
    margin-top: 1vw;
  }
  p,
  li {
    font-size: 2.4vw;
    width: 80%;
    margin-left: 5vw;
  }
  button {
    width: 20vw;
    padding: 2vw;
    border-radius: 2vw;
    margin-bottom: 4vw;
    margin-right: 7vw;
    margin-left: 7vw;
  }
  .staffCon {
    margin: 1vw;
    width: 46%;
  }
  .staffRole {
    font-size: 2.8vw;
  }
  .container__box {
    width: 80vw;
  }
  .staffPfp {
    height: 20vw;
    width: 20vw;
    margin-top: 5vw;
  }
}
@media only screen and (max-width: 768px) {
  li,
  p {
    font-size: 3vw;
  }
  #gradient {
    height: 130vw;
  }
  .staffRole {
    font-size: 3vw;
  }
}
@media only screen and (max-width: 576px) {
  .staffCon {
    width: 100%;
  }
  #gradient {
    height: 155vw;
  }
  button {
    width: 26vw;
    margin-right: 3vw;
    margin-left: 3vw;
  }
  li,
  p {
    font-size: 3.7vw;
  }
  .staffRole {
    font-size: 5.7vw;
  }
  .caption {
    font-size: 3vw;
  }
}
@media only screen and (max-width: 450px) {
  .caption {
    font-size: 5vw;
  }
  .subtext {
    font-size: 6vw;
  }
  h1 {
    font-size: 4vw;
  }
  #gradient {
    height: 230vw;
  }
  h2 {
    font-size: 3.8vw;
  }
  p,
  li {
    font-size: 4vw;
  }
  .staffRole {
    font-size: 5.6vw;
  }
  button {
    width: 28vw;
    margin-right: 3vw;
    margin-left: 3vw;
  }
}
@media only screen and (max-width: 356px) {
  h1 {
    font-size: 6vw;
  }
  h2 {
    font-size: 5vw;
  }
  p,
  li {
    font-size: 5vw;
  }
  #gradient {
    height: 260vw;
  }
  button {
    width: 27vw;
    margin-right: 3vw;
    margin-left: 3vw;
  }
  .staffRole {
    font-size: 5.7vw;
  }
}
</style>

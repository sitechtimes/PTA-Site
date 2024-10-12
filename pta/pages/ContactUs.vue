<template>
  <div>
    <div id="gradient"></div>
    <div>
      <h1 class="heading">CONTACTS</h1>
    </div>
    <div class="buttons">
      <button
        class="contacts-type"
        @click="(shownDiv = 'join'), tester()"
        v-bind:style="{ backgroundColor: joinColor }"
        :class="{ shown: shownDiv === 'join' }"
      >
        Join Us
      </button>
      <button
        class="contacts-type"
        @click="(shownDiv = 'staff'), tester()"
        v-bind:style="{ backgroundColor: staffColor }"
        :class="{ shown: shownDiv === 'staff' }"
      >
        Staff
      </button>

      <button
        class="contacts-type"
        @click="(shownDiv = 'sol'), tester()"
        v-bind:style="{ backgroundColor: solColor }"
        :class="{ shown: shownDiv === 'sol' }"
      >
        SLT
      </button>
    </div>
    <div v-if="shownDiv === 'staff'" class="container__box">
      <!-- <h1 class="subh">Board Members</h1> -->
      <div id="staff">
        <div class="staffCon" v-for="people in staff">
          <img class="staffPfp" :src="people.image" :alt="people.name" />
          <h3 class="subtext">{{ people.name }}</h3>
          <h4 class="staffRole">{{ people.roles }}</h4>
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
      <!-- <h1 class="subh">School Leadership Team</h1> -->
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
        <!-- <h1 class="subh">Join Us</h1> -->
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
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  props: ["TogglePopup"],
  data() {
    return {
      staff: Array,
      shownDiv: "join",
      staffColor: "transparent",
      joinColor: "white",
      solColor: "transparent",
      slt: Array,
    };
  },
  methods: {
    async getStaff() {
      const query = queryContent("/staff").sort({ roles: 1 }).find();
      query.then((response) => {
        this.staff = response;
      });
    },
    async getSLT() {
      const query = queryContent("/slt").find();
      query.then((response) => {
        this.slt = response;
      });
    },
    tester() {
      if (this.shownDiv === "join") {
        this.joinColor = "white";
        this.staffColor = "transparent";
        this.solColor = "transparent";
      } else if (this.shownDiv === "staff") {
        this.joinColor = "transparent";
        this.staffColor = "white";
        this.solColor = "transparent";
      } else {
        this.joinColor = "transparent";
        this.staffColor = "transparent";
        this.solColor = "white";
      }
    },
  },

  mounted() {
    let tl = gsap.timeline();
    tl.from(".popup", { scale: 0.3, duration: 0.4 });
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
#outside {
  background: transparent;
  height: 100vh;
  width: 100vw;
}
.popup-inner {
  margin-left: 0;
}
.message {
  font-weight: 350;
  font-size: 1.5rem;
  width: 95%;
  margin: 3% 0 0 0%;
}
.c {
  font-weight: 350;
  font-size: 1.5rem;
  width: 90%;
  margin: 0% 0 0 0%;
}
.messageh {
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
  left: 70%;
  background: transparent;
  position: fixed;
  top: 0%;
  font-size: 2vw;
  cursor: pointer;
}
.popup-close:hover {
  background: transparent;
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
  background-color: white;
  width: 65vw;
  margin-left: auto;
  margin-right: auto;
  margin-top: 2vw;
  padding: 3vw;
  padding-top: 2.5vw;
  border-radius: 1.5rem;
  color: #483221;
  font-family: var(--font-heading);
  margin-bottom: 10vw;
}
.container__ParentVolunteer {
  margin-top: 1.5rem;
}
h1 {
  text-align: center;
  font-size: 2.5vw;
}
h2 {
  margin-left: 5vw;
  margin-top: 1vw;
  font-size: 2vw;
}

li,
p {
  font-size: 1.2vw;
  margin-left: 5vw;
  margin-right: 5vw;
}
p {
  margin-top: 0.7vw;
  margin-bottom: 0.7vw;
}
h3,
h4,
a {
  margin: 0;
  overflow-x: hidden;
}
.contacts-type {
  font-size: 1.8vw;
  padding: 0.5rem 0.7rem;
}
.subh {
  margin-top: 0;
  margin-bottom: 0;
}
.staffCon {
  margin: 0vw, 1.2vw;
  overflow-x: hidden;
  width: 15vw;
}
.subtext {
  font-weight: bolder;
  font-size: 1.35vw;
}
.staffPfp {
  height: 10vw;
  width: 10vw;
  overflow-x: hidden;
  border-radius: 50%;
}
#staff {
  display: flex;
  justify-content: flex-start;
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
  font-size: 1.3vw;
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
#staff {
  display: flex;
  justify-content: start;
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
  p {
    font-size: 2vw;
  }
  li {
    font-size: 2vw;
  }
  h2 {
    font-size: 2vw;
  }
  #gradient {
    height: 80vw;
  }
  .contacts-type {
    font-size: 2.8vw;
  }
  .container__box {
    width: 80vw;
  }
  #staff {
    display: flex;
    justify-content: center;
    text-align: center;
    flex-wrap: wrap;
    overflow-x: hidden;
  }
  .staffCon {
    width: 15vw;
    margin: 4vw;
  }
  .staffPfp {
    height: 14vw;
    width: 14vw;
  }
  .subtext {
    font-size: 1.7vw;
  }
  .caption {
    font-size: 1.3vw;
  }
  .staffRole {
    font-size: 1.5vw;
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
    width: 28%;
    margin: 2rem 1rem;
  }
  .staffRole {
    font-size: 1.6vw;
  }
  h2 {
    font-size: 2vw;
  }
}
@media only screen and (max-width: 820px) {
  .contacts-type {
    font-size: 1.6rem;
  }
  .subtext {
    font-size: 2.3vw;
  }

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
    width: 30%;
  }
  .staffRole {
    font-size: 2vw;
  }
  .container__box {
    width: 80vw;
  }
  .staffPfp {
    height: 14vw;
    width: 14vw;
    margin-top: 5vw;
  }
}
@media only screen and (max-width: 768px) {
  li,
  p {
    font-size: 2.3vw;
  }
  #gradient {
    height: 130vw;
  }
  .staffRole {
    font-size: 1.9vw;
    margin-top: 0.3vh;
  }
  .subtext {
    font-size: 2.3vw;
    margin-top: 0.5rem;
  }
  .subh {
    font-size: 2rem;
    margin-bottom: 0;
    margin-top: 1rem;
  }
  .staffPfp {
    height: 10vw;
    width: 10vw;
    margin-top: 1.75rem;
  }
  .staffCon {
    width: 20vw;
    margin: 2.75vw;
  }
  .caption {
    font-size: 1.75vw;
  }
}
@media only screen and (max-width: 576px) {
  .staffCon {
    width: 20vw;
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
    font-size: 2.6vw;
  }
  .staffRole {
    font-size: 2.5vw;
  }
  .caption {
    font-size: 2vw;
  }
  .subh {
    font-size: 5vw;
  }
  .contacts-type {
    font-size: 4vw;
  }
}
@media only screen and (max-width: 450px) {
  .contacts-type {
    font-size: 1rem;
  }

  /* email address */
  .caption {
    font-size: 2.3vw;
    margin-top: 0;
  }
  /* name */
  .subtext {
    font-size: 3vw;
  }
  h1 {
    font-size: 3vw;
  }
  #gradient {
    height: 230vw;
  }
  h2 {
    font-size: 3.3vw;
  }
  p,
  li {
    font-size: 3vw;
  }

  .staffRole {
    font-size: 3vw;
  }
  .staffPfp {
    height: 20vw;
    width: 20vw;
    margin-top: 0.5rem;
  }
  button {
    width: 28vw;
    margin-right: 3vw;
    margin-left: 3vw;
  }
  .staffCon {
    margin: 4vw;
    padding: 0;
    width: 7.5rem;
  }
  .subh {
    font-size: 1.5rem;
  }
  #staff {
    display: flex;
    justify-content: center;
    text-align: center;
    flex-wrap: wrap;
    overflow-x: hidden;
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
    font-size: 3.5vw;
  }
  .subtext {
    font-size: 4.5vw;
  }
  .staffCon {
    margin: 3vw;
    width: 8rem;
  }
}
</style>

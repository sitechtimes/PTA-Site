<template>
  <div>
    <div id="gradient"></div>
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
      <Footer />
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
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
        this.staffColor = "transparent";
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
    this.getSLT();
    this.getStaff();
    gsap.from(".container__box", {
      duration: 0.5,
      y: 100,
      delay: 0.5,
      opacity: 0,
    });
    gsap.from(".buttons", {
      duration: 0.5,
      y: 100,
      opacity: 0,
    });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);
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

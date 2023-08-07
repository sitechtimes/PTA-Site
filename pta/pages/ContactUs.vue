<template>
  <div>
    <div id="gradient"></div>
    <div>
      <h2 id="heading">CONTACTS</h2>
    </div>
    <div class="buttons">
      <button
        @click="shownDiv = 'staff'"
        :class="{ shown: shownDiv === 'staff' }"
      >
        Staff
      </button>
      <button
        @click="shownDiv = 'join'"
        :class="{ shown: shownDiv === 'join' }"
      >
        Join Us
      </button>
    </div>
    <div v-if="shownDiv === 'staff'" class="container__box">
      <h1>Board Members</h1>
      <div id="staff">
        <div class="staffCon" v-for="people in staff">
          <img class="staffPfp" :src="people.image" :alt="people.name" />
          <h3 class="staffName">{{ people.name }}</h3>
          <h4 class="staffRole">{{ people.roles }}</h4>
          <a
            class="staffEmail"
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
        <h1>Join Us</h1>
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
    };
  },
  methods: {
    async getStaff() {
      const query = queryContent("/staff").find();
      console.log(query);
      query.then((response) => {
        this.staff = response;
      });
    },
  },
  mounted() {
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
h1 {
  text-align: center;
  font-size: 2.5vw;
}
h2 {
  font-size: 1.7vw;
}

li,
p {
  font-size: 1vw;
}
p {
  margin-top: 2vw;
  margin-bottom: 2vw;
}
#footer {
  margin-top: -10vw;
}
.container__box {
  overflow-x: hidden;
  background-color: #fcf6e9;
  width: 65vw;
  margin-left: auto;
  margin-right: auto;
  margin-top: 2vw;
  padding: 3vw;
  border-radius: 3vw;
  color: #483221;
  font-family: var(--font-heading);
}
h3,
h4,
a {
  margin: 0;
  overflow-x: hidden;
}
.staffCon {
  margin: 3vw;
  overflow-x: hidden;
  width: 15vw;
}
.staffPfp {
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

#heading {
  position: relative;
  text-align: center;
  color: #483221;
  font-family: var(--font-heading);
  font-size: 3vw;
  font-style: normal;
  font-weight: 800;
  line-height: auto;
  letter-spacing: 0.1rem;
  margin: 0;
  margin-top: 3vw;
  z-index: 0;
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
@media (max-width: 2000px) {
  .staffName {
    font-size: 1.6vw;
  }
  .staffRole {
    font-size: 1.3vw;
  }
  .staffEmail {
    font-size: 1.2vw;
  }
  #join {
    padding-bottom: 10vw;
  }
  h1 {
    text-align: center;
    font-size: 2.5vw;
    margin-top: 0;
  }
  h2 {
    font-size: 1.7vw;
  }

  li,
  p {
    font-size: 1vw;
  }
  p {
    margin-top: 2vw;
    margin-bottom: 2vw;
  }
  #footer {
    margin-top: -10vw;
  }
  .container__box {
    overflow-x: hidden;
    background-color: #fcf6e9;
    width: 65vw;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2vw;
    padding: 3vw;
    border-radius: 2vw;
    color: #483221;
    font-family: var(--font-heading);
  }
  h3,
  h4,
  a {
    margin: 0;
    overflow-x: hidden;
  }
  .staffCon {
    margin: 3vw;
    overflow-x: hidden;
    width: 15vw;
  }
  .staffPfp {
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

  #heading {
    position: relative;
    text-align: center;
    color: #483221;
    font-family: var(--font-heading);
    font-size: 3vw;
    font-style: normal;
    font-weight: 800;
    line-height: auto;
    letter-spacing: 0.1rem;
    margin: 0;
    margin-top: 3vw;
    z-index: 0;
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
}
@media (max-width: 920px) {
  .staffCon {
    width: 40%;
  }
  .staffName {
    font-size: 2.5vw;
  }
  .staffRole {
    font-size: 2vw;
  }
}
@media (max-width: 820px) {
  h2 {
    font-size: 3vw;
    margin-left: 5vw;
    width: 60%;
    margin-top: 5vw;
  }
  .staffEmail {
    font-size: 4vw;
  }
  h1 {
    font-size: 4vw;
    margin-top: 5vw;
  }
  #heading {
    font-size: 7vw;
    margin-top: 10vw;
    margin-bottom: 10vw;
    text-align: center;
    margin-right: auto;
    margin-left: auto;
  }
  p {
    font-size: 3vw;
  }
  li {
    font-size: 3vw;
  }
  p,
  li {
    width: 80%;
    margin-left: 5vw;
  }
  button {
    width: 25vw;
    font-size: 4vw;
    padding: 3vw;
    border-radius: 5vw;
    margin-bottom: 4vw;
    margin-right: 7vw;
    margin-left: 7vw;
  }
  .staffCon {
    width: 100%;
  }
  .container__box {
    width: 80vw;
  }
  .staffPfp {
    width: 60%;
    margin-top: 5vw;
  }
  .staffName {
    font-size: 5vw;
  }
  .staffRole {
    font-size: 4vw;
  }
}
</style>

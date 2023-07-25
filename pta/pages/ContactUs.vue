<template>
  <div class="container__ContactUs">
    <div id="gradient">
      <div class="container">
        <div class="container__Navigation">
          <button
            class="button__navigation"
            :class="{ active: currentSection === 'GeneralContacts' }"
            @click="showSection('GeneralContacts')"
          >
            Contacts
          </button>
          <button
            class="button__navigation"
            :class="{ active: currentSection === 'BoardMembers' }"
            @click="showSection('BoardMembers')"
          >
            Board
          </button>
          <button
            class="button__navigation"
            :class="{ active: currentSection === 'JoinUs' }"
            @click="showSection('JoinUs')"
          >
            Join Us
          </button>
        </div>

        <div class="container__Body">
          <section
            id="section__GeneralContacts"
            v-show="currentSection === 'GeneralContacts'"
          >
            <div class="container__box">
              <h1>General Contacts</h1>
              <PTAInformation id="PTAInformation" />
            </div>
          </section>

          <section
            id="section__BoardMembers"
            v-show="currentSection === 'BoardMembers'"
          >
            <div class="container__box">
              <h1>Board Members</h1>
              <div class="container__BoardMembers">
                <div class="container__BoardMembers-profile">
                  <img src="/profile.svg" alt="Profile Picture Filler" />
                  <h3>John Doe • Position</h3>
                  <a
                    href="mailto:johndoe@gmail.com"
                    target="_blank"
                    rel="noopener"
                  >
                    johndoe@gmail.com
                  </a>
                </div>
                <div class="container__BoardMembers-profile">
                  <img src="/profile.svg" alt="Profile Picture Filler" />
                  <h3>John Doe • Position</h3>
                  <a
                    href="mailto:johndoe@gmail.com"
                    target="_blank"
                    rel="noopener"
                  >
                    johndoe@gmail.com
                  </a>
                </div>
              </div>
            </div>
          </section>

          <section id="section__JoinUs" v-show="currentSection === 'JoinUs'">
            <div class="container__box">
              <h1>Join Us</h1>
              <div class="container__ParentVolunteer">
                <h2>PARENT VOLUNTEER OPPORTUNITIES</h2>
                <p>
                  If you would like to volunteer at PTA events, please print out
                  the attached volunteer form and submit to the PTA Room or
                  email it to
                  <a
                    href="mailto:sitechpta@gmail.com"
                    target="_blank"
                    rel="noopener"
                    >sitechpta@gmail.com</a
                  >.
                </p>
                <p>Be part of the SI TECH PTA Grant Committee</p>
                <ul>
                  <li>
                    The grants committee researches and applies for grants to
                    help fund school programs and activities including
                    classroom/school upgrades, art, technology, maker-space, and
                    the library. We reach out to foundations and corporations.
                  </li>
                  <li>
                    Volunteers are needed to research grant opportunities or
                    help write the grant proposals. No prior experience is
                    necessary, time commitment is contingent on grant deadlines.
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
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  data() {
    return {
      currentSection: "GeneralContacts", //the current section by default is the 'General Contacts' section
    };
  },
  methods: {
    showSection(section) {
      this.currentSection = section; //the current section by default is the 'General Contacts' section
    },
  },
  mounted() {
    gsap.from(".container__box", {
      duration: 0.5,
      y: 100,
      delay: 0.5,
      opacity: 0,
    });
    gsap.from(".container__Navigation", {
      duration: 0.5,
      y: 100,
      opacity: 0,
    });
  },
};
</script>

<style scoped>
@import url(../assets/base.css);

#container__Navigation {
}
#section__BoardMembers {
}
#section__JoinUs {
}

/* #gradient {
  width: 100vw;
  height: 100vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: linear-gradient(180deg,
      #ffc498 0%,
      #ffd88c 20%,
      #fce5ac 34%,
      #fbefd7 44%,
      #fff 55%);
} */

.container {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 15vh;
  height: fit-content;
  width: 100vw;
  align-content: center;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  overflow-x: hidden;
  overflow-y: hidden;
}

#gradient {
  width: 100%;
  height: fit-content;
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
  overflow-y: hidden;
}

.container__ContactUs {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: auto;
  align-items: center;
  justify-content: center;
}

.container__Navigation {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  margin-right: 0;
  margin-left: 0;
  width: 70vw;
  display: flex;
}

#container_Body {
  width: 100vw;
}

.container__box {
  width: 70vw;
  background-color: #fcf6e9;
  border-radius: 1.5rem;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  padding: 2rem;
  padding-bottom: 2em;
  padding-top: 2em;
  margin: 2rem;
  overflow-x: hidden;
  word-wrap: break-word;
}

.container__BoardMembers {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  overflow-x: hidden;
}

.container__BoardMembers-profile {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 2rem;
  padding: 0;
  overflow-x: hidden;
}

.container__BoardMembers-profile p {
  text-align: center;
}

.container__BoardMembers-profile img {
  width: 9rem;
}

.container__ParentVolunteer {
  width: 60vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-left: 3rem;
}

h1 {
  color: #483221;
  text-align: center;
  font-family: var(--font-heading);
  font-size: 2rem;
  font-style: normal;
  font-weight: 800;
  line-height: normal;
  letter-spacing: 0.05rem;
  margin: 1rem;
}

h2 {
  color: #483221;
  font-family: var(--font-heading);
  font-size: 1.8rem;
  font-style: normal;
  font-weight: 800;
  line-height: auto;
  letter-spacing: 0.1rem;
  margin: 0;
}

h3 {
  color: var(--text-color);
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: 0;
  text-align: center;
}

p,
li {
  color: #483221;
  font-family: var(--font-text);
  font-size: 1.45rem;
  font-style: normal;
  font-weight: 500;
  line-height: 130%;
}

a {
  font-family: var(--font-text);
  font-size: 1.45rem;
  font-style: normal;
  font-weight: 500;
  line-height: 2rem;
}

button {
  /* margin: 1rem; */
  padding: 1rem;
  padding-left: 2vw;
  padding-right: 2vw;
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
  background-color: transparent;
  cursor: pointer;
}

button.active {
  background-color: #fcf6e9;
}

section {
  display: flex;
  flex-wrap: nowrap;
  align-content: center;
  justify-content: center;
}
@media only screen and (min-width: 1200px) {
  .container {
    top: 10vh;
  }
  button {
    font-size: 1.5vw;
    margin-top: 6vw;
  }
}
@media only screen and (max-width: 1450px) {
  #section__JoinUs {
    height: 40rem;
  }
  p,
  li,
  a {
    font-size: 1.2rem;
  }
}
@media screen and (max-height: 1200px) {
  #gradient {
    height: 100vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  .container__ContactUs {
    height: 100vh;
  }

  /* button {
    width: 17vw;
  } */
}
@media only screen and (max-width: 1200px) {
  #section__JoinUs {
    height: 40rem;
  }
  p,
  li,
  a {
    font-size: 1.1rem;
  }
  .container__box {
    padding: 0;
    height: fit-content;
  }
  .container {
    top: 6vh;
  }
  button {
    font-size: 2vw;
    margin-top: 10vw;
  }
}

@media only screen and (max-width: 992px) {
  button {
    font-size: 2.5vw;
    margin-top: 10vw;
  }
}

@media screen and (max-width: 992px) {
  .container {
    top: 3vh;
  }

  button {
    width: 20vw;
  }
  #section__JoinUs {
    height: 43rem;
  }
  p,
  li,
  a {
    font-size: 1.1rem;
  }
  h2 {
    font-size: 1.5rem;
  }
}

@media screen and (max-height: 992px) and (orientation: landscape) {
  #gradient {
    height: 120vh;
  }
  .container__ContactUs {
    height: 90vh;
  }
}
@media screen and (max-width: 768px) and (orientation: landscape) {
  button {
    font-size: 2vw;
    margin-top: 10vw;
  }
  h1 {
    font-size: 3vw;
  }
  .container__TextInformation {
    font-size: 0.1vw;
  }
}

@media screen and (max-width: 768px) and (orientation: portrait) {
  button {
    font-size: 3vw;
    margin-top: 15vw;
  }
}
@media screen and (max-width: 768px) {
  button {
    width: 23vw;
  }
  #gradient {
    height: 110vh;
  }
  .container__ContactUs {
    height: 100vh;
  }
  #section__JoinUs {
    height: 48rem;
  }
  .container__ParentVolunteer {
    margin: 5px auto;
  }
  p,
  li,
  a {
    font-size: 1.03rem;
  }
  h2 {
    font-size: 1.2rem;
  }
}

@media screen and (max-height: 768px) {
  #gradient {
    height: 160vh;
  }
  .container__ContactUs {
    height: 130vh;
  }
}
@media screen and (max-width: 576px) {
  .container__Navigation {
    margin-top: 1rem;
  }
  #gradient {
    height: 15vh;
  }
  .container__ContactUs {
    height: 14vh;
  }
}
@media screen and (max-height: 576px) {
  .container__Navigation {
    margin-top: 3rem;
  }
  #gradient {
    height: 13vh;
  }
  .container__ContactUs {
    height: 13vh;
  }
}
@media only screen and (max-width: 576px) {
  #gradient {
    height: 142vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  #PTAInformation {
    margin-top: 0.5rem;
  }
  .container {
    top: 10vh;
  }
  .container__box {
    width: 80vw;
    border-radius: 1rem;
  }
  #section__JoinUs {
    height: 200vw;
  }
  .container__ContactUs {
    display: flex;
    flex-direction: column;
    height: 160vw;
    align-items: center;
    justify-content: center;
  }
  .container__BoardMembers-profile {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 2rem;
  }
  .container__BoardMembers-profile img {
    width: 25vw;
  }
  .container__Navigation {
    width: 90vw;
  }
  h1 {
    font-size: 4vw;
  }
  h2 {
    color: #483221;
    font-family: var(--font-heading);
    font-size: 3vw;
  }
  h3 {
    font-size: 5vw;
    line-height: 2rem;
    margin-bottom: 0.8rem;
  }
  p,
  li {
    color: #483221;
    font-family: var(--font-text);
    font-size: 3vw;
    font-style: normal;
    font-weight: 500;
  }
  a {
    font-family: var(--font-text);
    font-size: 3vw;
    font-style: normal;
    font-weight: 500;
    line-height: 1.5rem;
  }
  button {
    font-size: 3.5vw;
    border-radius: 1rem;
    margin-bottom: 0;
    margin-top: 5vw;
    width: 20vw;
  }
}
</style>

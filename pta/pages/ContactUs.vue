<template>
  <div id="gradient">
    <div class="container__ContactUs">
      <div class="container__Navigation">
        <button
          class="button__navigation"
          :class="{ active: currentSection === 'GeneralContacts' }"
          @click="showSection('GeneralContacts')"
        >
          General Contacts
        </button>
        <button
          class="button__navigation"
          :class="{ active: currentSection === 'BoardMembers' }"
          @click="showSection('BoardMembers')"
        >
          Board Members
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
            <PTAInformation />
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
                the attached volunteer form and submit to the PTA Room or email
                it to
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
                  The grants committee researches and applies for grants to help
                  fund school programs and activities including classroom/school
                  upgrades, art, technology, maker-space, and the library. We
                  reach out to foundations and corporations.
                </li>
                <li>
                  Volunteers are needed to research grant opportunities or help
                  write the grant proposals. No prior experience is necessary,
                  time commitment is contingent on grant deadlines.
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
</template>

<script>
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
};
</script>

<style scoped>
@import url(../assets/base.css);

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

#gradient {
  width: 100vw;
  height: 100vh;
  padding: 0%;
  position: absolute;
  top: 0%;
  left: 0%;
  background: linear-gradient(180deg, #ffd88c 0%, rgba(217, 217, 217, 0) 100%);
}
.container__ContactUs {
  display: flex;
  flex-direction: column;
  height: 100vh;
  align-items: center;
}

.container__Navigation {
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100vw;
  margin-top: 8rem;
}

.container__box {
  width: 70vw;
  height: auto;
  background-color: #fcf6e9;
  border-radius: 3.25rem;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  padding: 2rem;
  margin: 2rem;
}

.container__BoardMembers {
  display: flex;
  flex-direction: row;
}

.container__BoardMembers-profile {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 2rem;
}

.container__BoardMembers-profile img {
  width: 9rem;
}

.container__ParentVolunteer {
  width: 60vw;
  margin-left: 3rem;
}

h1 {
  color: #483221;
  text-align: center;
  font-family: var(--font-heading);
  font-size: 2.5rem;
  font-style: normal;
  font-weight: 800;
  line-height: normal;
  letter-spacing: 0.05rem;
  margin: 2rem 1rem;
  text-decoration: #ffd88c underline;
}

h2 {
  color: #483221;
  font-family: var(--font-heading);
  font-size: 2rem;
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
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 130%;
}

a {
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 2rem;
}

button {
  margin: 1rem;
  padding: 1rem;
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: auto;
  font-family: var(--font-heading);
  color: var(--text-color);
  border-radius: 1.25rem;
  border: none;
  transition: background-color 0.3s ease;
  background-color: transparent;
  cursor: pointer;
}

button.active {
  background-color: #fcf6e9;
}
</style>

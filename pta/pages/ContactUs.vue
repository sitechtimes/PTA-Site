<template>
  <div class="container" id="gradient">
    <div class="container__NavigationButtons" id="btncon">
      <button class="button__navigation" @click="showSection('GeneralContacts')">
        <h3>General Contacts</h3>
      </button>
      <button class="button__navigation" @click="showSection('BoardMembers')">
        <h3>Board Members</h3>
      </button>
      <button class="button__navigation" @click="showSection('JoinUs')">
        <h3>Join Us</h3>
      </button>
    </div>

    <div class="container__body">
      <section id="section__GeneralContacts" v-show="currentSection === 'GeneralContacts'">
        <div class="container__box">
          <h1>General Contacts</h1>
          <PTAInformation />
        </div>
      </section>
      <section id="section__BoardMembers" v-show="currentSection === 'BoardMembers'">
        <div class="container__box">
          <h1>Board Members</h1>
          <div class="container__BoardMembers">
            <div class="container__BoardMembers-profile">
              <img src="/profile.svg" alt="Profile Picture Filler" />
              <h4>John Doe • Position</h4>
              <a href="mailto:johndoe@gmail.com" target="_blank" rel="noopener">
                johndoe@gmail.com
              </a>
            </div>
            <div class="container__BoardMembers-profile">
              <img src="/profile.svg" alt="Profile Picture Filler" />
              <h4>John Doe • Position</h4>
              <a href="mailto:johndoe@gmail.com" target="_blank" rel="noopener">
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
              If you would like to volunteer at PTA events, please print out the attached volunteer form and submit to
              the PTA Room or email it to
              <a href="mailto:sitechpta@gmail.com" target="_blank" rel="noopener">sitechpta@gmail.com</a>.
            </p>
            <p>Be part of the SI TECH PTA Grant Committee</p>
            <ul>
              <li>
                The grants committee researches and applies for grants to help fund school programs and activities
                including classroom/school upgrades, art, technology, maker-space, and the library. We reach out to
                foundations and corporations.
              </li>
              <li>
                Volunteers are needed to research grant opportunities or help write the grant proposals. No prior
                experience is necessary, time commitment is contingent on grant deadlines.
              </li>
              <li>
                Please email
                <a href="mailto:SITHSptagrantcommittee@gmail.com" target="_blank" rel="noopener">SITHSptagrantcommittee@gmail.com</a>
                if interested.
              </li>
            </ul>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSection: 'GeneralContacts' //the current section by default is the 'General Contacts' section 
    };
  },
  methods: {
    showSection(section) {
      this.currentSection = section; //the current section by default is the 'General Contacts' section 
    }
  }
};
</script>

<style scoped>
@import "../assets/base.css";

#gradient {
  width: 100vw;
  height: 100%;
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
  overflow-x: hidden;
}

.container {
  width: 100%;
  height: 100%;
  padding: 0;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.container__NavigationButtons {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  position: fixed;
  z-index: 2;
  width: 100%;
  top: 0;
  left: 0;
  margin-top: 5rem;
  margin-bottom: 5rem;
}

.container__body {
  flex: 1;
  overflow-y: auto;
  position: fixed;
  z-index: 1;
  margin-top: 10rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.container__box {
  width: 77rem;
  height: 43.5rem;
  background-color: #FCF6E9;
  border-radius: 3.25rem;
  display: flex;
  flex-direction: column;
  align-content: center;
  padding: 2rem;
  margin: 2rem;
  margin-top: 5rem;
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

.container__BoardMembers p,
.container__BoardMembers h4 {
  margin: 0.5rem 0 0 0;
}

.container__BoardMembers-profile img {
  width: 9rem;
}

.container__ParentVolunteer {
  width: 60vw;
}

.button__navigation {
  margin: 1rem;
  padding: 1rem;
  background-color: #FCF6E9;
  border-radius: 1.25rem;
  border: none;
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
  line-height: 129.164%;
  letter-spacing: 0.1rem;
}

h3 {
  font-family: var(--font-heading);
  color: var(--text-color);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: auto;
  margin: 0;
}

h4 {
  color: var(--text-color);
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  text-align: center;
}

button {
  margin: 1rem;
  padding: 1rem;
  background-color: #FCF6E9;
  border-radius: 1.25rem;
  border-color: none;
}

p,
li {
  color: #483221;
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 129.164%;
}

.container__NavigationButtons button {
  text-decoration: none;
  color: #483221;
  text-align: center;
  font-family: var(--font-heading);
  line-height: 2rem;
  cursor: pointer;
}

a {
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 2rem;
}

@media only screen and (max-width: 576px) {
  .container__box {
    width: 100%;
    height: auto;
    margin-bottom: 2rem;
  }

  .container__ParentVolunteer {
    width: 92vw;
  }

  .container__BoardMembers {
    flex-direction: column;
    align-items: center;
  }

  .container__BoardMembers-profile {
    margin: 1rem 0;
  }
}
</style>

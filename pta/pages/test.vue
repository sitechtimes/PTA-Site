<template>
    <div class="whole">
        <div id="gradient">
        <div class="parent">
            <div class="div1">
                <h1>1</h1>
                <div class="container__SideNavigation" id="btncon">
                    <a href="#section__GeneralContacts" class="sidenavbtn">
                        <h3>General Contacts</h3>
                    </a>
                    <a id="boardMembers" href="#section__BoardMembers" class="sidenavbtn">
                        <h3>Board Members</h3>
                    </a>
                    <a id="joinUs" href="#section__JoinUs" class="sidenavbtn">
                        <h3>Join Us</h3>
                    </a>
                </div>
            </div>
            <div class="div2">
                <h1>2</h1>
                <section id="section__GeneralContacts">
          <div class="container__box">
            <h1>General Contacts</h1>
            <PTAInformation />
          </div>
        </section>
        <section id="section__BoardMembers">
          <div class="container__box">
            <h1>Board Members</h1>
            <div class="container__BoardMembers">
              <div class="container__BoardMembers-profile">
                <img src="/profile.svg" alt="Profile Picture Filler">
                <h4>John Doe • Position</h4>
                <a href="https://mail.google.com/mail/u/1/?view=cm&fs=1&to=johndoe@gmail.com.com&tf=1" target="_blank"
                  rel="noopener">
                  johndoe@gmail.com
                </a>
              </div>
              <div class="container__BoardMembers-profile">
                <img src="/profile.svg" alt="Profile Picture Filler">
                <h4>John Doe • Position</h4>
                <a href="https://mail.google.com/mail/u/1/?view=cm&fs=1&to=johndoe@gmail.com.com&tf=1" target="_blank"
                  rel="noopener">
                  johndoe@gmail.com
                </a>
              </div>
            </div>
          </div>
        </section>
        <section id="section__JoinUs">
          <div class="container__box">
            <h1>Join Us</h1>
            <div class="container__ParentVolunteer">
              <h2>PARENT VOLUNTEER OPPORTUNITIES</h2>
              <p>
                If you would like to volunteer at PTA events, please print out the attached volunteer form and
                submit to
                the PTA Room or email it to <a
                  href="https://mail.google.com/mail/u/1/?view=cm&fs=1&to=sitechpta@gmail.com.com&tf=1" target="_blank"
                  rel="noopener">sitechpta@gmail.com</a>.
              </p>
              <p>Be part of the SI TECH PTA Grant Committee</p>
              <ul>
                <li>
                  The grants committee researches and applies for grants to help fund school programs and
                  activities
                  including classroom/school upgrades, art, technology, maker-space, and the library. We reach
                  out
                  to
                  foundations and corporations.
                </li>
                <li>
                  Volunteers are needed to research grant opportunities or help write the grant proposals. No
                  prior
                  experience is necessary, time commitment is contingent on grant deadlines.
                </li>
                <li>
                  Please email <a
                    href="https://mail.google.com/mail/u/1/?view=cm&fs=1&to=SITHSptagrantcommittee@gmail.com.com&tf=1"
                    target="_blank" rel="noopener">SITHSptagrantcommittee@gmail.com</a> if interested.
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

<style scoped>
h1 {
    text-align: center;
}

#gradient {
  width: 100vw;
  height: 180vh;
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

.parent {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
    border: 1px solid black;
}

.div1 {
    grid-area: 1 / 1 / 2 / 2;
    border: 1px solid black;
}

.div2 {
    grid-area: 1 / 2 / 2 / 3;
    border: 1px solid black;
}

@import url(../assets/base.css);


section {
  padding: 2rem;
  height: 100vh;
}

html,
body {
  overflow-x: hidden;
  margin: 0;
  height: 100%;
}

.container {
  background: linear-gradient(180deg, #FFD88C 0%, rgba(217, 217, 217, 0.00) 100%);
  width: 100vw;
  height: 100%;
  padding: 0%;
  position: relative;
  display: flex;
  top: 0;
  left: 0;
}

.container__box {
  width: 77rem;
  height: 43.5rem;
  background-color: #FCF6E9;
  border-radius: 3.25rem;
  box-shadow: 2rem 2rem #FFD88C;
  border: 1px solid #000;
  display: flex;
  flex-direction: column;
  align-content: center;
  padding: 2rem 2rem 2rem 5rem;
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
  font-size: 2rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
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

p,
li {
  color: #483221;
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 129.164%;
}

.container__SideNavigation a {
  text-decoration: none;
}

a {
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 129.164%;
}

.container__SideNavigation {
  width: 20vw;
  padding: 2rem;
  padding-top: 8rem;
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  overflow-y: auto;
}

/* .container__body::before {
  content: "";s
  position: fixed;
  display: flex;
  flex-direction: row;
  justify-content: center;
  top: 0;
  right: 80%;
  width: 0.1rem;
  height: 70%;
  background-color: var(--text-color);
}
 */
.container__body {
  flex: 1;
  margin-left: 20vw;
  height: 100vh;
  overflow-y: auto;
}

.container__ParentVolunteer {
  width: 60vw;
}

@media only screen and (max-width: 576px) {
  section {
    padding: 1rem;
    margin-top: 25vw;
    height: auto;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: auto;
  }

  .container__body {
    height: 80vh;
    width: 100%;
    padding: 0;
    margin: 0;
  }

  p {
    font-size: 1rem;
  }

  li {
    font-size: 1rem;
  }

  h1 {
    font-size: 2rem;
  }

  a {
    font-size: 1rem;
  }

  h2 {
    font-size: 1.5rem;
    letter-spacing: 0.1rem;
    text-align: center;
  }

  h4 {
    font-size: 1.2rem;
  }

  .container__BoardMembers-profile img {
    width: 8rem;
  }

  .container__ParentVolunteer {
    width: 92vw;
  }

  .container__BoardMembers {
    width: 100vw;
    display: flex;
    flex-direction: row;
    flex-shrink: 1;
  }

  #btncon {
    display: none;
  }
}

@media screen and (max-width: 1366px) {
  section {
    padding: 1rem;
    height: auto;
    margin-top: 3rem;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: auto;
  }

  .container__body {
    height: 80vh;
    width: 100%;
    padding: 0;
    margin: 0;
  }

  p {
    font-size: 1rem;
  }

  li {
    font-size: 1rem;
  }

  h1 {
    font-size: 2rem;
  }

  a {
    font-size: 1rem;
  }

  h2 {
    font-size: 1.5rem;
    letter-spacing: 0.1rem;
    text-align: center;
  }

  h4 {
    font-size: 1.2rem;
  }

  .container__BoardMembers-profile img {
    width: 8rem;
  }

  .container__ParentVolunteer {
    width: 80vw;
  }

  .container__BoardMembers {
    width: 100vw;
    display: flex;
    flex-direction: row;
    flex-shrink: 1;
  }

  #btncon {
    display: none;
  }
}

@media screen and (min-width: 576px) {}

/* media queries max width
    sm:	 ≥576px
 	md:  ≥768px
    lg:	 ≥992px
    xl:  ≥1200px
    xxl: ≥1400px
    */
</style>
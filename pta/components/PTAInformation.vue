<template>
  <div class="container__PTAInformation">
    <div class="container__SocialMedias">
      <!-- <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/facebook.svg" alt="facebook icon" />
      </a>
      <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/instagram.svg" alt="instagram icon" />
      </a>
      <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/twitter.svg" alt="twitter icon" />
      </a> -->
      <div class="container__SMLayout">
        <h2>Instagram</h2>
        <h3>Follow S.I. Tech news and events on Instagram at:</h3>
        <a href="https://www.instagram.com/_sammytheseagull"
          >Sammy the Seagull</a
        >
        <a href="https://www.instagram.com/merlenwein">Principal Erlenwein</a>
      </div>
      <div class="container__SMLayout">
        <h2>Facebook</h2>
        <h3>
          Facebook Follow S.I. Tech news and events on Facebook. Like our page
          and you'll receive S.I.
        </h3>
        <a href="https://www.facebook.com/SITECHPTA/">SITHS PTA Facebook</a>
      </div>
      <div class="container__SMLayout">
        <h2>Twitter</h2>
        <h3>Follow S.I. Tech news and events on Twitter.</h3>
        <a href="https://www.twitter.com/SITech_HS">SITHS PTA Twitter</a>
      </div>
      <div class="container__SMLayout">
        <h2>Naviance</h2>
        <h3>
          Actively engage in career, college and scholarship searches, the
          college application process and receive school communication via
          Naviance.
        </h3>
        <a
          href="https://connection.naviance.com/family-connection/auth/login/?hsid=siths"
          >SITHS Naviance</a
        >
      </div>
    </div>
    <div class="container__TextInformation">
      <p>sitechpta@gmail.com</p>
      <p>485 Clawson Street, Staten Island, NY 10306</p>
    </div>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);
a {
  font-family: var(--font-text);
  font-size: 1.45vw;
  font-style: normal;
  font-weight: 500;
  color: var(--text-color);
  line-height: 2rem;
  margin: 0;
}
h2 {
  color: var(--text-color);
  font-family: var(--font-heading);
  font-size: 1.7rem;
  font-style: normal;
  font-weight: 800;
  line-height: auto;
  margin: 0;
}

h3 {
  color: var(--text-color);
  font-size: 1.5vw;
  line-height: 0;
  font-family: var(--font-text);
  font-weight: 500;
  line-height: 130%;
  margin: 0;
}
.container__SMLayout {
  width: 16vw;
  display: flex;
  flex-direction: column;
  align-items: left;
  margin: 10px;
}
.container__SocialMedias {
  display: flex;
  flex-direction: row;
  width: fit-content;
  margin: 30px;
  margin-bottom: 0.5rem;
}

.container__TextInformation {
  display: flex;
  flex-direction: column;
  justify-content: left;
  align-items: left;
}

.container__PTAInformation {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
p {
  font-family: var(--font-text);
  color: var(--text-color);
  text-align: center;
  font-size: 1.7vw;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin: 0.5rem;
}

@media only screen and (max-width: 1200px) {
  h3,
  a {
    font-size: 1.2rem;
  }
}
@media only screen and (max-width: 992px) {
  h3,
  a {
    font-size: 1.1rem;
    line-height: 1.1rem;
  }
}
@media only screen and (max-width: 768px) {
  h2 {
    font-size: 1.3rem;
  }
  p {
    font-size: 1rem;
  }
  .container__SMLayout {
    width: 60vw;
    display: flex;
    flex-direction: column;
    margin: 10px;
  }
  .container__SocialMedias {
    display: flex;
    flex-direction: column;
    width: fit-content;
    margin: 1vw;
    margin-bottom: 0.5rem;
  }
  .container__PTAInformation {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
@media only screen and (max-width: 356px) {
  h3,
  a {
    font-size: 6vw;
  }
}
</style>

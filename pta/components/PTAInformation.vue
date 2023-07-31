<template>
  <div class="container__PTAInformation">
    <div class="container__SocialMedias">
      <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/facebook.svg" alt="facebook icon" />
      </a>
      <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/instagram.svg" alt="instagram icon" />
      </a>
      <a href=" " target="_blank" rel="noopener">
        <img src="/SocialMedias/twitter.svg" alt="twitter icon" />
      </a>
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
  line-height: 1.1px;
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
  width: 15rem;
  justify-content: space-evenly;
  margin-bottom: 0.5rem;
}

.container__TextInformation {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
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
  font-size: 2vw;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin: 0.5rem;
}

@media only screen and (max-width: 768px) {
  p {
    font-size: 1rem;
  }
}
</style>

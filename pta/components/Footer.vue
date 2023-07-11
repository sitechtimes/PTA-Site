<template>
  <div id="footer">
    <h2>Keep in touch with us!</h2>
    <div id="so_med">
      <a
        href="https://www.facebook.com/SITECHPTA/"
        target="_blank"
        rel="noopener"
      >
        <img src="../assets/SoMed_Logos/facebook.svg" alt="facebook icon" />
      </a>
      <a href=" " target="_blank" rel="noopener">
        <img src="../assets/SoMed_Logos/instagram.svg" alt="instagram icon" />
      </a>
      <a
        href="https://twitter.com/sitechpta?s=21&t=dZH_wZg5Nkoix7CNanukPQ"
        target="_blank"
        rel="noopener"
      >
        <img src="../assets/SoMed_Logos/twitter.svg" alt="twitter icon" />
      </a>
    </div>
    <div id="text">
      <p>sitechpta@gmail.com</p>
      <p>485 Clawson Street, Staten Island, NY 10306</p>
    </div>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);

#footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: flex-end;
  position: absolute;
  bottom: 0;
  left: 1%;
  right: 1%;
}

#so_med {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  padding-top: 0.625rem;
  padding-bottom: 0.625rem;
}

h2 {
  color: var(--text-color);
  text-align: center;
  font-family: var(--font-heading);
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  letter-spacing: 0.05rem;
}

p {
  font-family: var(--font-text);
  color: var(--text-color);
  text-align: center;
  font-size: 1.125rem;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin: 0.313rem;
}

@media screen and (max-width: 576px) {
  h2 {
    font-size: 5.25vw;
    margin-bottom: 3vw;
  }
  img {
    height: 6vw;
    width: 7vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  p {
    font-size: 3.5vw;
  }
}

@media screen and (min-width: 576px) {
  h2 {
    font-size: 5.25vw;
    margin-bottom: 3vw;
  }
  img {
    height: 6vw;
    width: 7vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  p {
    font-size: 3.5vw;
  }
}

@media screen and (min-width: 576px) and (orientation: landscape){
  h2 {
    font-size: 2.25vw;
    margin-bottom: 1vw;
  }
  img {
    height: 4vw;
    width: 5vw;
    padding-right: 2vw;
    padding-left: 2vw;
  }
  p {
    font-size: 2vw;
  }
  #so_med{
    margin-bottom: -.75vw;
  }
}

@media screen and (min-width: 768px) {
  h2 {
    font-size: 4.25vw;
    margin-bottom: 3vw;
  }
  img {
    height: 5vw;
    width: 6vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  p {
    font-size: 3vw;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
  h2 {
    font-size: 2.25vw;
    margin-bottom: 1vw;
  }
  img {
    height: 4vw;
    width: 5vw;
    padding-right: 3vw;
    padding-left: 3vw;
  }
  p {
    font-size: 1.75vw;
  }
  #so_med{
    margin-bottom: -.75vw;
  }
}

@media screen and (min-width: 866px) {
  h2 {
    font-size: 4vw;
    margin-bottom: 3vw;
  }
  img {
    height: 4.5vw;
    width: 5.5vw;
    padding-right: 3vw;
    padding-left: 3vw;
  }
  p {
    font-size: 3vw;
  }
}

@media screen and (min-width: 866px) and (orientation: landscape) {
  h2 {
    font-size: 2.25vw;
    margin-bottom: 1.5vw;
  }
  img {
    height: 4vw;
    width: 5vw;
    padding-right: 3vw;
    padding-left: 3vw;
  }
  p {
    font-size: 1.7vw;
  }
  #so_med{
    margin-bottom: -.75vw;
  }
}

@media screen and (min-width: 992px) {
  h2 {
    font-size: 2.25vw;
    margin-bottom: 1.5vw;
  }
  img {
    height: 4vw;
    width: 5vw;
    padding-right: 3vw;
    padding-left: 3vw;
  }
  p {
    font-size: 1.75vw;
  }
}
</style>

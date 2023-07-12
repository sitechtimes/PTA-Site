<template>
  <footer>
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
  </footer>
</template>

<style scoped>
@import url(../assets/base.css);
img:hover {
  opacity: 0.7;
}
img {
  transition: 0.3s;
}
#footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-bottom: 15px;
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
  #footer {
    width: 55vw;
    transform: translate(-50%, 0);
  }
  h2 {
    font-size: 4.25vw;
    margin-bottom: 2vw;
  }
  img {
    height: 6vw;
    width: 7vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  p {
    font-size: 3.25vw;
  }
}

@media screen and (min-width: 576px) {
  h2 {
    font-size: 4vw;
    margin-bottom: 3vw;
  }
  img {
    height: 6vw;
    width: 7vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  p {
    font-size: 3vw;
  }
}

@media screen and (min-width: 576px) and (orientation: landscape) {
  h2 {
    font-size: 1.8vw;
    margin-bottom: 0.5vw;
  }
  img {
    height: 3vw;
    width: 4vw;
    padding-right: 1.5vw;
    padding-left: 1.5vw;
  }
  p {
    font-size: 1.75vw;
  }
  #so_med {
    margin-bottom: -1.4vw;
  }
}

@media screen and (min-width: 768px) {
  #footer {
    width: 50vw;
    transform: translate(-50%, 0);
  }
  h2 {
    font-size: 3.2vw;
    margin-bottom: 3vw;
  }
  img {
    height: 5vw;
    width: 6vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  #so_med {
    margin-bottom: 1vw;
  }
  p {
    font-size: 2.4vw;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
  h2 {
    font-size: 1.85vw;
    margin-bottom: 0.3vw;
  }
  img {
    height: 3vw;
    width: 4vw;
    padding-right: 2vw;
    padding-left: 2vw;
  }
  p {
    font-size: 1.5vw;
  }
  #so_med {
    margin-bottom: -0.75vw;
  }
}

@media screen and (min-width: 866px) {
  #footer {
    width: 55vw;
    transform: translate(-50%, 0);
  }
  h2 {
    font-size: 3.5vw;
    margin-bottom: 3.5vw;
  }
  img {
    height: 4.5vw;
    width: 5vw;
    padding-right: 3.75vw;
    padding-left: 3.75vw;
  }
  p {
    font-size: 2.5vw;
  }
}

@media screen and (min-width: 866px) and (orientation: landscape) {
  h2 {
    font-size: 1.8vw;
    margin-bottom: 0.3vw;
  }
  img {
    height: 3vw;
    width: 5vw;
    padding-right: 1.75vw;
    padding-left: 1.75vw;
  }
  p {
    font-size: 1.4vw;
  }
  #so_med {
    margin-bottom: -0.75vw;
  }
}

@media screen and (min-width: 992px) {
  h2 {
    font-size: 1.5vw;
    margin-bottom: 1vw;
  }
  img {
    height: 3vw;
    width: 5vw;
    padding-right: 1.75vw;
    padding-left: 1.75vw;
  }
  p {
    font-size: 1.2vw;
  }
  #so_med {
    margin-bottom: -0.1vw;
  }
}

@media screen and (min-width: 1300px) {
  h2 {
    font-size: 1.5vw;
    margin-bottom: 1.15vw;
  }
  img {
    height: 3vw;
    width: 5vw;
    padding-right: 1.75vw;
    padding-left: 1.75vw;
  }
  p {
    font-size: 1.2vw;
  }
  #so_med {
    margin-bottom: 0.5vw;
  }
}
</style>

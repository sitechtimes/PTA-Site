<template>
  <div class="container__footer">
    <h2>Staten Island Technical High School PTA</h2>
    <div id="so_med">
      <a
        href="https://www.facebook.com/SITECHPTA/"
        target="_blank"
        rel="noopener"
      >
        <img src="../assets/SoMed_Logos/facebook.svg" alt="facebook icon" />
      </a>
      <a href="https://www.instagram.com/_sammytheseagull/" target="_blank" rel="noopener">
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

.container__footer {
  text-align: center;
  z-index: 1000;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-content: flex-end;
  background: var(--footer-bg);
  height: fit-content;
  border-radius: 19px;
  width: 58rem;
  margin: auto;
  margin-bottom: 4rem;
  padding: 1rem;
}
img {
  padding: 0 2rem;
  transition: 0.3s;
}

img:hover {
  opacity: 0.7;
}

#so_med {
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding-top: 0.625rem;
  padding-bottom: 0.625rem;
}

h2 {
  color: var(--text-color);
  text-align: center;
  font-family: var(--font-heading);
  font-style: normal;
  font-weight: 400;
  font-size: 1.5rem;
  margin-top: 0;
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
@media screen and (max-width: 1400px) {
  #footer {
    bottom: 0px;
  }
  p {
    font-size: 1.2vw;
  }
  #so_med {
    margin-bottom: 0.5vw;
  }
}

@media screen and (max-width: 1200px) {
  .container__footer {
    width: 40rem;
  }
  p {
    font-size: 1rem;
  }
}

@media screen and (max-width: 992px) {
  p {
    font-size: 1.1rem;
  }
}

@media screen and (max-width: 768px) {
  h2 {
    font-size: 20px;
    margin-bottom: 10px;
  }

  img {
    height: 5vw;
    width: 6vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }

  #so_med {
    margin-bottom: 0.5rem;
    padding: 0.2rem;
  }

  p {
    font-size: 1.2rem;
  }
  .container__footer {
    width: 80vw;
  }
}

@media screen and (max-width: 576px) {
  h2 {
    font-size: 4.25vw;
  }

  p {
    font-size: 3.5vw;
  }

  img {
    height: 6vw;
    width: 7vw;
    padding-right: 5vw;
    padding-left: 5vw;
  }
}
</style>

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
  left: 30%;
  right: 30%;
}

#so_med {
  display: flex;
  flex-direction: row;
  width: 15rem;
  justify-content: space-evenly;
  padding-top: 10px;
  padding-bottom: 10px;
}

h2 {
  color: var(--text-color);
  text-align: center;
  font-family: var(--font-heading);
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  letter-spacing: 0.8px;
}

p {
  font-family: var(--font-text);
  color: var(--text-color);
  text-align: center;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  margin: 5px;
}

@media screen and (max-width: 768px) {
  img {
    height: 80%;
    width: 80%;
  }
}
@media screen and (max-width: 425px) {
  h2 {
    font-size: 20px;
  }
  img {
    height: 80%;
    width: 80%;
  }
  p {
    font-size: 15px;
  }
}
@media screen and (max-width: 320px) {
  h2 {
    font-size: 15px;
  }
  img {
    height: 70%;
    width: 70%;
  }
  p {
    font-size: 10px;
  }
}
</style>

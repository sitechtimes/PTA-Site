<template>
  <div class="space">
    <div class="container__footer">
      <h2 class="subtext">Staten Island Technical High School PTA</h2>
      <div id="so_med">
        <a
          href="https://www.facebook.com/SITECHPTA/"
          target="_blank"
          rel="noopener"
        >
          <img src="../assets/SoMed_Logos/facebook.svg" alt="facebook icon" />
        </a>
        <a
          href="https://www.instagram.com/_sammytheseagull/"
          target="_blank"
          rel="noopener"
        >
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
      <div class="caption">
        <p class="email">sitechpta@gmail.com</p>
        <p class="address">485 Clawson Street, Staten Island, NY 10306</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url(../assets/base.css);

.container__footer {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  align-content: center;
  z-index: 2;
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
  background: white;
  border-radius: 19px;
  width: 50rem;
  padding: 1rem;
  margin-bottom: 3rem;
  /* box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px; */
}
.subtext {
  margin-top: 0.5rem;
  margin-bottom: 0.7rem;
  font-weight: bold;
}
.caption {
  margin-top: 0;
}
.email {
  margin-bottom: 0;
  margin-top: 0.5rem;
}
.address {
  margin-top: 0.5rem;
}
img {
  padding: 0 2rem;
  transition: 0.3s;
  width: 1.8rem;
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
.space {
  height: 16rem;
}
@media screen and (max-width: 1400px) {
  #footer {
    bottom: 0px;
  }
  #so_med {
    margin-bottom: 0.5vw;
  }
}

@media screen and (max-width: 1200px) {
  .container__footer {
    width: 40rem;
  }
}

@media screen and (max-width: 992px) {
  img {
    width: 1.6rem;
  }
  .space {
    height: 14rem;
  }
}

@media screen and (max-width: 768px) {
  .space {
    height: 14rem;
  }
  img {
    width: 1.6rem;
    padding-right: 5vw;
    padding-left: 5vw;
  }

  #so_med {
    margin-bottom: 0.5rem;
    padding: 0.2rem;
  }
  .container__footer {
    width: 80vw;
  }
}

@media screen and (max-width: 576px) {
  img {
    width: 1.6rem;
    padding-right: 5vw;
    padding-left: 5vw;
  }
  #so_med {
    margin-bottom: 0;
  }
}
</style>

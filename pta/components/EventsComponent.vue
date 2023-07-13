<template>
    <!-- The values in the headings should be inputted by the user, but I inputted values to test it and to orient it properly -->
    <div class="events">
      <a
        href="https://www.theatlantic.com/science/archive/2017/06/cat-domination/530685/"
        class="event"
      >
        <div class="text">
          <h3 class="name">Jessie's Birthday</h3>
          <h3 class="date">05/06</h3>
        </div>
        <div class="flag"></div>
      </a>
      <a
        href="https://www.fundraiserinsight.org/wp-content/uploads/2013/07/bake-sale-fundraiser.jpg"
        class="event"
      >
        <div class="text">
          <h3 class="name">Bake Sale</h3>
          <h3 class="date">05/10</h3>
        </div>
        <div class="flag"></div>
      </a>
      <a
        href="https://www.siths.org/apps/pages/index.jsp?uREC_ID=1553703&type=d&pREC_ID=1679764"
        class="event"
      >
        <div class="text">
          <h3 class="name">SITHS</h3>
          <h3 class="date">05/17</h3>
        </div>
        <div class="flag"></div>
      </a>
    </div>
  </template>
  <style scoped>
  @import url(../assets/base.css);
  
  .events {
    margin: 3% 5%;
    display: flex;
    width: 59%;
    height: 24rem;
    flex-direction: column;
    justify-content: space-around;
  }
  a,
  a:hover,
  a:focus,
  a:active {
    text-decoration: none;
    color: inherit;
  }
  .flag {
    border-radius: 8px;
    width: 3.125rem;
    height: 3.5rem;
    margin: -5px 0 0 60px;
    padding-top: 15px;
    position: relative;
    background: var(--text-color);
  }
  .flag:after {
    content: " ";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 0;
    height: 0;
    border-bottom: 0.813rem solid white;
    border-left: 1.563rem solid transparent;
    border-right: 1.563rem solid transparent;
  }
  
  .date {
    font-family: Karla;
    font-weight: 400;
  }
  .name {
    margin-left: 10%;
    color: var(--text-color);
    font-family: Karla;
    font-weight: 400;
  }
  .text {
    display: flex;
    align-items: center;
    flex-direction: row;
    justify-content: space-between;
    width: 80%;
    height: 100%;
  }
  .event {
    display: flex;
    width: 100%;
    height: 6rem;
    background-color: white;
    border-radius: 1.3rem;
    background: #ffffff;
    box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
    transition: 0.2s;
    flex-wrap: wrap;
  }
  @media screen and (max-width: 1400px) {
    .flag {
      width: 2.188rem;
      border-radius: 5px;
      height: 2rem;
    }
    .flag:after {
      border-left: 1.063rem solid transparent;
      border-right: 1.063rem solid transparent;
    }
    .name,
    .date {
      margin: 3%;
      font-size: 30px;
    }
    .event {
      height: 40%;
      margin: 0.6rem;
    }
    .events {
      margin: 3% 5%;
      height: 24%;
    }
  }
  @media screen and (max-width: 1200px) {
    .events {
      margin: 3% 5%;
      height: 24%;
    }
    .event {
      margin: 0.6rem;
      border-radius: 12px;
    }
    .flag {
      width: 2rem;
    }
    .flag:after {
      border-left: 1rem solid transparent;
      border-right: 1rem solid transparent;
    }
    .name,
    .date {
      font-size: 30px;
    }
  }
  @media screen and (max-width: 992px) {
    .events {
      margin: 3% 5%;
      height: 18.31%;
    }
    .flag {
      width: 30px;
      border-radius: 5px;
      padding-top: 5px;
      height: 1.5rem;
    }
    .flag:after {
      border-left: 15px solid transparent;
      border-right: 15px solid transparent;
    }
    .event {
      border-radius: 10px;
    }
    .name,
    .date {
      font-size: 25px;
    }
  }
  @media screen and (max-width: 768px) {
    .events {
      margin: 3% 5%;
      width: 80%;
      height: 18.31%;
    }
    .flag {
      width: 25px;
      border-radius: 5px;
      padding-top: 5px;
      height: 2.5rem;
      left: 6%;
      margin-top: -3px;
    }
    .flag:after {
      border-left: 12.5px solid transparent;
      border-right: 12.5px solid transparent;
    }
    .event {
      border-radius: 7px;
    }
    .name,
    .date {
      font-size: 25px;
    }
  }
  @media screen and (max-width: 576px) {
    .events {
      box-sizing: border-box;
      margin: auto;
      width: 85%;
      height: 18.31%;
    }
    .flag {
      width: 1.2rem;
      padding-top: 0.6rem;
      height: 1.3rem;
      margin-top: -3px;
      margin-left: -2%;
    }
    .event {
      height: 16rem;
    }
    .flag:after {
      border-left: 0.6rem solid transparent;
      border-right: 0.6rem solid transparent;
    }
    .name {
      font-size: 1rem;
    }
    .date {
      font-size: 1rem;
    }
  }
  @media screen and (max-width: 356px) {
    .flag {
      width: 1.2rem;
      padding-top: 0.6rem;
      height: 1.3rem;
      margin-top: -3px;
      margin-left: -4%;
    }
  }
  </style>
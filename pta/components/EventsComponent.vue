<template>
  <div class="event">
    <div class="text">
      <h3 class="name">Jessie's Birthday</h3>
      <h3 class="date">05/06</h3>
    </div>
    <div class="flag"></div>
  </div>
  <div class="event">
    <div class="text">
      <h3 class="name">Bake Sale</h3>
      <h3 class="date">05/10</h3>
    </div>
    <div class="flag"></div>
  </div>
  <div class="event">
    <div class="text">
      <h3 class="name">SITHS</h3>
      <h3 class="date">05/17</h3>
    </div>
    <div class="flag"></div>
  </div>
</template>
<style scoped>
@import url(../assets/base.css);

.flag {
  border-radius: 8px;
  width: 50px;
  height: 56px;
  margin: -5px 50px 0 0;
  padding-top: 15px;
  position: relative;
  background: var(--text-color);
  transition: 0.8s;
}
.flag:after {
  content: " ";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 0;
  border-bottom: 13px solid white;
  border-left: 25px solid transparent;
  border-right: 25px solid transparent;
}
.flag:hover {
  padding-top: 90px;
}
.date {
  margin-right: 10%;
  font-family: Karla;
  font-weight: 400;
}
.name {
  display: inline;
  margin-left: 10%;
  color: var(--text-color);
  font-family: Karla;
  font-weight: 400;
}
.text {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 80%;
}
.event {
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 20%;
  background-color: white;
  border-radius: 20px;
  background: #ffffff;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  transition: 0.5s;
}
.event:hover {
  height: 40%;
}
@media screen and (max-width: 1400px) {
}
@media screen and (max-width: 1200px) {
  .flag {
    width: 35px;
    border-radius: 5px;
    height: 50px;
    left: 6%;
  }
  .flag:after {
    border-left: 17px solid transparent;
    border-right: 17px solid transparent;
  }
  .name,
  .date {
    margin: 3%;
    font-size: 30px;
  }
}
@media screen and (max-width: 992px) {
  .flag {
    width: 30px;
    border-radius: 5px;
    padding-top: 5px;
    height: 40px;
    left: 6%;
  }
  .flag:after {
    border-left: 15px solid transparent;
    border-right: 15px solid transparent;
  }
  .name,
  .date {
    margin: 4%;
    font-size: 25px;
  }
}

@media screen and (max-width: 768px) {
  .flag {
    width: 25px;
    border-radius: 5px;
    padding-top: 5px;
    height: 40px;
    left: 6%;
    margin-top: -3px;
  }
  .flag:after {
    border-left: 12.5px solid transparent;
    border-right: 12.5px solid transparent;
  }
  .name,
  .date {
    margin: 3%;
    font-size: 25px;
  }
}
@media screen and (max-width: 576px) {
  .flag {
    width: 25px;
    border-radius: 5px;
    padding-top: 5px;
    height: 30px;
    left: 5%;
    margin-top: -3px;
  }
  .event {
    height: 25%;
  }
  .flag:after {
    border-left: 12.5px solid transparent;
    border-right: 12.5px solid transparent;
  }
  .name,
  .date {
    margin: 3%;
    font-size: 20px;
  }
}
</style>

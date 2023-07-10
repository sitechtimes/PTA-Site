<template>
  <h3>Events</h3>
  <div class="event">
    <h3 class="name">Jessie's Birthday</h3>
    <h3 class="date">05/06</h3>
  </div>
</template>
<style scoped>
@import url(../assets/base.css);
.date {
  display: inline;
}
.name {
  display: inline;
  margin-left: 10%;
  display: flex;
  height: 85px;
  flex-direction: column;
  justify-content: center;
  color: #483221;
  font-family: Karla;
}
.event {
  width: 659px;
  height: 84px;
  background-color: white;
  border-radius: 20px;
  background: #ebebeb;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
}
</style>

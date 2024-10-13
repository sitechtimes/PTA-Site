<template>
  <div class="section">
    <h1 class="subh">SITHS EVENTS</h1>
    <iframe
      id="sithsCal"
      class="cal"
      src="https://calendar.google.com/calendar/embed?height=700&wkst=1&ctz=America%2FNew_York&bgcolor=%23ffffff&src=YmM3MzI4NWRjNGQ2YTQzNjFiZmFmNzZjYjkzMjlkYzMyY2Y2ZDUyODA4M2QxZTdiMmVlNTVjMDNhMzI0ODIxN0Bncm91cC5jYWxlbmRhci5nb29nbGUuY29t&color=%238E24AA"
      style="border: solid 1px #777"
      frameborder="0"
      scrolling="no"
    >
    </iframe>
  </div>
</template>

<script setup></script>

<style lang="css" scoped>
@import url(../assets/base.css);

#sithsCal {
  display: flex;
  margin: auto;
  margin-top: 3rem;
  width: 83vw;
  height: 50vw;
}

.subh {
  text-align: center;
  margin: 0;
  margin-top: 4rem;
}
@media screen and (max-width: 992px) {
  #sithsCal {
    width: 80%;
    height: 60vw;
    margin-top: 1rem;
    margin-bottom: 2rem;
  }
  .subh {
    margin-top: 2rem;
  }
}

@media screen and (max-width: 768px) {
  #sithsCal {
    width: 70%;
  }
}

@media screen and (max-width: 576px) {
  #sithsCal {
    width: 80%;
    height: 60vw;
    margin-bottom: 2rem;
    margin-top: 1rem;
  }
}
</style>

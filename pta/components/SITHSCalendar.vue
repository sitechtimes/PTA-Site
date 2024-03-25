<template>
    <h1 class="heading2">SITHS EVENTS</h1>
    <div class="section">
        <iframe 
            id="calendar" 
            class="cal2"
            src="https://calendar.google.com/calendar/embed?height=700&wkst=1&ctz=America%2FNew_York&bgcolor=%23ffffff&src=YmM3MzI4NWRjNGQ2YTQzNjFiZmFmNzZjYjkzMjlkYzMyY2Y2ZDUyODA4M2QxZTdiMmVlNTVjMDNhMzI0ODIxN0Bncm91cC5jYWxlbmRhci5nb29nbGUuY29t&color=%238E24AA" 
            style="border:solid 1px #777" 
            frameborder="0" 
            scrolling="no">
        </iframe> 
        </div>
</template>

<script>
</script>

<style lang="css" scoped>
@import url(../assets/base.css);


#calendar{
    display: flex;
    margin: auto;
    margin-top: 3rem;
    width: 83vw; 
    height: 70vh;
}

.heading{
    text-align: center;
    margin: 0;
    margin-top: 4rem;
}
@media screen and (max-width: 992px) {

  #calendar {
    width: 80%;
    height: 60vw;
    margin-bottom: 2rem;
  }
}

@media screen and (max-width: 768px) {
  #calendar {
    width: 70%;
  }
  .heading{
    text-align: center;
    margin: 0;
    margin-top: 3rem;
    margin-bottom: 2rem;
}
}



@media screen and (max-width: 576px) {

  #calendar {
    width: 80%;
    height: 60vw;
    margin-bottom: 2rem;
    margin-top: 1rem;
  }
}


</style> 
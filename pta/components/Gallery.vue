<template>
    <!-- Slider container -->
    <div class="slider">
      <!-- Bind key to the loop index to get unique key for each slide -->
      <div v-for="(slide, index) in slides" :key="index" class="slide" :style="{ transform: `translateX(${100 * (index - curSlide)}%)` }">
        <img :src="slide" alt="" />
      </div>
  
      <!-- Control buttons -->
      <button class="btn btn-next" @click="nextSlide"> <p>►</p></button>
      <button class="btn btn-prev" @click="prevSlide"><p>◄</p> </button>
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        slides: [
          "https://source.unsplash.com/random?landscape,mountain",
          "https://source.unsplash.com/random?landscape,cars",
          "https://source.unsplash.com/random?landscape,night",
          "https://source.unsplash.com/random?landscape,city"
        ],
        curSlide: 0
      };
    },
    methods: {
      nextSlide() {
        // Increment the current slide index, and reset if it reaches the maximum
        this.curSlide = (this.curSlide + 1) % this.slides.length;
      },
      prevSlide() {
        // Decrement the current slide index, and reset if it becomes negative
        this.curSlide = (this.curSlide - 1 + this.slides.length) % this.slides.length;
      }
    }
  };
  </script>
  <style scoped>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    height: 100vh;
    display: grid;
    place-items: center;
  }
  
  .slider {
    width: 100%;
    max-width: 800px;
    height: 490px;
    position: relative;
    overflow: hidden; 
   
  }
  .slide {
    width: 100%;
    max-width: 800px;
    height: 25.5vw;
    position: absolute;
    transition: all 0.5s;
  }
  
  .slide img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 15px;
  }
  
  .btn {
    position: absolute;
    width: 40px;
    height: 40px;
    padding: 10px;
    border: none;
    border-radius: 50%;
    z-index: 10px;
    cursor: pointer;
    background-color: #fff;
    font-size: 18px;
  }
  .btn:active {
    transform: scale(1.1);
  }
  .btn-prev {
    top: 45%;
    left: 2%;
  }
  
  .btn-next {
    top: 45%;
    right: 2%;
  }

@media screen and (max-width: 1400px) {
  .slide {}
  .slider{height: 380px;}
}
@media screen and (max-width: 1200px) {  
  .slide {}
  .slider{
    max-width: 446px;
    height: 317px;
  }
}
@media screen and (max-width: 992px) {  
  .slide {
    height: 30vw;
  }
  .slider{   
    max-width: 600px;
    height: 309px;
  }
}
@media screen and (max-width: 768px) {  
  .slide {
    height: 30vw;
  }
  .slider{    
    max-width: 600px;
    height: 229px;
  }
}
@media screen and (max-width: 576px) {  
  .slide {
    height: 40vw;
  }
  .slider{    
    max-width: 600px;
    height: 249px;
  }
}
@media  screen and (max-width: 450px) {  
  .slide {    
    height: 50vw;
  }
  .slider{    
    max-width: 600px;
    height: 201px;
  }
}
@media  screen and (max-width: 356px) {  
  .btn-prev, .btn-next{}
}
@media screen and (min-width: 576px) {
}
@media screen and (min-width: 576px) and (orientation: landscape) {
}
@media screen and (min-width: 768px) {
}
@media screen and (min-width: 768px) and (orientation: landscape) {
}
  </style>
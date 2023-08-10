<template>
  <!-- Slider container -->
  <div class="slider">
    <!-- Bind key to the loop index to get unique key for each slide -->
    <div
      v-for="(photo, index) in gallery"
      :key="index"
      class="slide"
      :style="{ transform: `translateX(${100 * (index - curSlide)}%)` }"
    >
      <img :src="photo.image" alt="Gallery PTA images" />
    </div>
    <!-- Control buttons -->
    <button class="btn btn-next" @click="nextSlide"><p>►</p></button>
    <button class="btn btn-prev" @click="prevSlide"><p>◄</p></button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      gallery: Array,
      curSlide: 0,
    };
  },
  methods: {
    async getGallery() {
      const query = queryContent("/gallery").find();
      console.log(query);
      query.then((response) => {
        this.gallery = response;
      });
    },
    nextSlide() {
      // Increment the current slide index, and reset if it reaches the maximum
      this.curSlide = (this.curSlide + 1) % this.gallery.length;
    },
    prevSlide() {
      // Decrement the current slide index, and reset if it becomes negative
      this.curSlide =
        (this.curSlide - 1 + this.gallery.length) % this.gallery.length;
    },
  },
  mounted() {
    this.getGallery();
  },
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
  height: 25vw;
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
  top: 44%;
  left: 2%;
  margin-left: 0.2rem;
}

.btn-next {
  top: 44%;
  right: 2%;
  margin-right: 0.2rem;
}

@media only screen and (max-width: 1400px) {
  .btn-prev,
  .btn-next {
    top: 39%;
  }
  .slider {
    height: 380px;
  }
}
@media only screen and (max-width: 1200px) {
  .slider {
    max-width: 600px;
    height: 370px;
  }
}
@media only screen and (max-width: 1024px) {
  .slide {
    height: 35vw;
  }
}
@media only screen and (max-width: 992px) {
  .slide {
    height: 35vw;
  }
  .slider {
    max-width: 550px;
    height: 350px;
  }
}
@media only screen and (max-width: 768px) {
  .slider {
    height: 350px;
    max-width: 450px;
  }
  .slide {
    height: 45vw;
  }
  .btn-prev,
  .btn-next {
    top: 39%;
  }
}
@media only screen and (max-width: 576px) {
  .slide {
    height: 45vw;
    margin-top: 2rem;
  }
  .slider {
    height: 300px;
    max-width: 400px;
  }
  .btn-prev,
  .btn-next {
    top: 50%;
  }
}
@media only screen and (max-width: 450px) {
  .slide {
    height: 55vw;
  }
  .slider {
    height: 280px;
  }
}
@media only screen and (max-width: 356px) {
  .slide {
    height: 58vw;
  }
  .slider {
    height: 250px;
  }
}
</style>

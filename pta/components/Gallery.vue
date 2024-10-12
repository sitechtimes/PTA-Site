<template>
  <div>
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
    </div>
    <div class="btncon">
      <button class="btn btn-prev" @click="prevSlide">prev</button>
      <button class="btn btn-next" @click="nextSlide">next</button>
    </div>
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
p {
  color: var(--text-color);
}
body {
  height: 100vh;
  display: grid;
  place-items: center;
}

.slider {
  width: 100%;
  max-width: 800px;
  height: 25vw;
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
.btncon {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  margin-top: 2rem;
}

.btn {
  width: 6rem;
  height: 2.5rem;
  border: none;
  border-radius: 5rem;
  z-index: 10;
  cursor: pointer;
  background-color: #fff;
  color: var(--text-color);
  font-size: 0.9rem;
  font-family: Karla;
  bottom: -2%;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  transition: background-color 0.5s;
}
.btn:hover {
  background-color: var(--text-color);
  color: #fff;
}
@media only screen and (max-width: 1400px) {
}
@media only screen and (max-width: 1200px) {
  .slide {
    height: 30vw;
  }
  .slider {
    max-width: 600px;
    height: 30vw;
  }
  .btncon {
    margin-top: 1.5rem;
  }
}
@media only screen and (max-width: 992px) {
  .slider {
    max-width: 550px;
    height: 40vw;
  }
  .slide {
    height: 40vw;
  }
}
@media only screen and (max-width: 768px) {
  .slider {
    height: 45vw;
    max-width: 520px;
  }
  .slide {
    height: 45vw;
  }
  /* .galBtn-prev,
  .galBtn-next {
    top: 42%;
  } */
}
@media only screen and (max-width: 576px) {
  /* .slide {
    margin-top: 2rem;
  } */
  .slider {
    max-width: 400px;
  }
  .btn {
    font-size: 0.8rem;
    width: 5rem;
    height: 2.2rem;
  }
  .btncon {
    margin-top: 1rem;
  }
  /* .galBtn-prev,
  .galBtn-next {
    top: 45%;
  } */
}
@media only screen and (max-width: 450px) {
  .slide {
    height: 55vw;
  }
  .slider {
    height: 55vw;
  }
  /* .galBtn-prev,
  .galBtn-next {
    top: 45%;
  } */
}
@media only screen and (max-width: 375px) {
  /* .galBtn-next {
    top: 43%;
  } */
}
@media only screen and (max-width: 375px) {
  .btn-next {
    top: 43%;
  }
}
@media only screen and (max-width: 356px) {
  .slide {
    height: 58vw;
  }
  .slider {
    height: 58vw;
  }
  p {
    font-size: 3vw;
  }
}
@media only screen and (max-width: 180px) {
  /* .galBtn-prev,
  .galBtn-next {
    top: 40vw;
  } */
  /* .galBtn {
    width: 20vw;
    height: 20vw;
  }
  p {
    font-size: 6vw;
  } */
}
</style>

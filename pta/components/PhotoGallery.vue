<template>
  <section class="container__carousel">
    <Carousel
      :items-to-show="2"
      :autoplay="2500"
      :wrap-around="true"
      :transition="500"
    >
      <Slide v-for="(image, index) in images" :key="index">
        <div class="carousel-item">
          <img :src="image" class="carousel-image" />
        </div>
      </Slide>

      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
  </section>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Pagination, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  name: "PhotoGallery",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      images: [
        "https://picsum.photos/seed/picsum/600/400",
        "https://picsum.photos/600/400?grayscale",
        "https://picsum.photos/600/400/?blur=2",
        /* insert src's or link to images here
        format:
        'image link',
        'image link',
        'image link' */
      ],
    };
  },
});
</script>

<style scoped>
.container__carousel {
  width: 40vw;
  margin: 2rem;
}

.carousel__slide {
  padding: 0.3125;
}

.carousel__viewport {
  perspective: 125rem;
}

.carousel__track {
  transform-style: preserve-3d;
}

.carousel-image {
  width: 30rem;
}

.carousel__slide--sliding {
  transition: 0.5s;
}

.carousel__slide {
  opacity: 0.9;
  transform: rotateY(-20deg) scale(0.9);
}
.carousel__slide--visible {
  transform: rotateY(0);
}
.carousel__slide--active ~ .carousel__slide {
  transform: rotateY(20deg) scale(0.9);
}

.carousel__slide--prev {
  opacity: 0.8;
  transform: rotateY(-10deg) scale(0.95);
}

.carousel__slide--next {
  opacity: 0.8;
  transform: rotateY(10deg) scale(0.95);
}

.carousel__slide--active {
  opacity: 1;
  transform: rotateY(0) scale(1.1);
  z-index: 100;
}

.carousel__pagination {
  margin: 1rem;
  padding: 0;
}

@media only screen and (max-width: 576px) {
  .container__carousel {
    width: 90vw;
  }

  .carousel-image {
    width: 20rem;
  }
}

@media screen and (max-width: 1024px) {
  .container__carousel {
    width: 70vw;
  }
}
</style>

<template>
  <section class="container__carousel">
    <Carousel :items-to-show="2.5" :wrap-around="true" :transition="500">
      <Slide v-for="(image, index) in images" :key="index">
        <div class="carousel-item">
          <img :src="image" class="carousel-image">
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
import { defineComponent } from 'vue'
import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'PhotoGallery',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      images: [
        'https://picsum.photos/seed/picsum/200/300',
        'https://picsum.photos/200/300?grayscale',
        'https://picsum.photos/200/300/?blur=2'
        /* insert src's or link to images here
        format:
        'image link',
        'image link',
        'image link' */
      ],
    }
  }
})
</script>

<style scoped>
.container__carousel {
  width: 50vw
}

.carousel-image {
  border-radius: 1rem;
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

.carousel__slide--sliding {
  transition: 0.5s;
}

.carousel__slide {
  opacity: 0.9;
  transform: rotateY(-20deg) scale(0.9);
}

.carousel__slide--active~.carousel__slide {
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

.carousel__pagination{
  margin: 1rem;
  padding: 0;
}

@media only screen and (max-width: 480px) {

  .container__carousel {
    width: 90vw;
  }
}
</style>

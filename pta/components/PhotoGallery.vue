<template>
  <div class="carousel">
    <!-- Photo 1 -->
    <input class="carousel-open" type="radio" id="carousel-1" name="carousel" checked="checked">
    <div class="carousel-item">
      <!--insert image here-->
    </div>

    <!-- Photo 2 -->
    <input class="carousel-open" type="radio" id="carousel-2" name="carousel" checked="checked">
    <div class="carousel-item">
      <!--insert image here-->
    </div>

    <!-- Navigation controls -->
    <label for="carousel-2" class="carousel-control next control-1">›</label>
    <label for="carousel-1" class="carousel-control prev control-2">‹</label>
  </div>
</template>
      
<style scoped>
.carousel-item {
  background-color: gray;
  width: 20rem;
  height: 20rem;
  border-radius: 1.5rem;
  position: absolute;
  opacity: 0;
  transition: opacity 1s ease-out;
}
input[type="radio"]{
    visibility:hidden;
}
.carousel-open:checked+.carousel-item {
  opacity: 100;
}

.carousel-control {
  color: #a5a988;
  cursor: pointer;
  display: none;
  font-size: 40px;
  height: 40px;
  line-height: 35px;
  top: 50%;
  transform: translate(0, -50%);
  text-align: center;
  width: 40px;
  z-index: 10;
}

.carousel-control.prev {
  left: 2%;
}

.carousel-control.next {
  right: 2%;
}

.carousel-control:hover {
  color: none;
}

/* Show navigation controls based on checked slide */
#carousel-1:checked~.control-1,
#carousel-2:checked~.control-2 {
  display: block;
}
</style>
      
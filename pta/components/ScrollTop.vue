<template>
  <div class="container__topArrow none-topArrow">
    <!-- <a href="#section__LandingSection"> -->
    <img
      class
      id="sttlaptop"
      src="/back-to-top-arrow.svg"
      @click="scroll"
      alt="scroll to top button"
    />
    <img
      id="sttmobile"
      src="/back-to-top-mobile.svg"
      @click="scroll"
      alt="scroll to top button"
    />
    <!-- </a> -->
  </div>
</template>

<script>
export default {
  // setup() {
  //   const showArrow = ref(false);
  //   const route = useRoute();
  //   return {
  //     showArrow,
  //     route,
  //   };
  // },
  methods: {
    ScrolledEnough: function () {
      const topArrow = document.querySelector(".container__topArrow");
      if (window.scrollY > 300) {
        topArrow.style.display = "flex";
        console.log("here");
        console.log(window.scrollY);
      } else {
        topArrow.style.display = "none";
        console.log("gone");
        console.log(window.scrollY);
      }
      // }
    },
    scroll() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
  mounted() {
    window.addEventListener("scroll", this.ScrolledEnough);
  },
};

/*
  } */
</script>

<style scoped>
.show-topArrow {
  opacity: 1;
}

.none-topArrow {
  opacity: 0;
}

.container__topArrow {
  z-index: 3;
  display: none;
  height: 3rem;
  opacity: 0.7;
  position: fixed;
  bottom: 1.25rem;
  right: 1.8rem;
  scroll-behavior: smooth;
  cursor: pointer;
}

@media screen and (max-width: 576px) {
  #sttlaptop {
    display: none;
  }

  .container__topArrow {
    height: 1.5rem;
    bottom: 9vw;
    right: 4%;
  }

  .container__topArrow img {
    height: 10vw;
  }
}

@media screen and (min-width: 576px) {
  #sttlaptop {
    display: none;
  }

  .container__topArrow {
    bottom: 6vw;
    right: 5%;
  }

  .container__topArrow img {
    height: 10vw;
  }
}

@media screen and (min-width: 576px) and (orientation: landscape) {
  #sttlaptop {
    display: none;
  }

  .container__topArrow {
    height: 1.5rem;
    bottom: 10%;
    right: 5%;
  }

  .container__topArrow img {
    height: 7vw;
  }
}

@media screen and (min-width: 768px) {
  .container__topArrow {
    height: 3vw;
    bottom: 10vw;
    right: 5%;
  }

  .container__topArrow img {
    height: 10vw;
  }
}

@media screen and (min-width: 768px) and (orientation: landscape) {
  #sttlaptop {
    display: none;
  }

  .container__topArrow {
    height: 3vw;
    bottom: 12%;
    right: 5%;
  }

  .container__topArrow img {
    height: 5.5vw;
  }
}

@media screen and (min-width: 866px) {
  .container__topArrow {
    height: 2rem;
    bottom: 9vw;
    right: 5%;
  }

  .container__topArrow img {
    height: 9vw;
  }
}

@media screen and (min-width: 866px) and (orientation: landscape) {
  .container__topArrow {
    height: 2rem;
    bottom: 7vw;
    right: 5%;
  }

  .container__topArrow img {
    height: 4rem;
  }
}

@media screen and (min-width: 992px) {
  .container__topArrow {
    height: 2rem;
    bottom: 8%;
    right: 5%;
  }

  .container__topArrow img {
    height: 5rem;
  }
}

@media screen and (min-width: 992px) and (orientation: landscape) {
  #sttmobile {
    display: none;
  }

  #sttlaptop {
    display: block;
  }

  .container__topArrow {
    height: 2rem;
    bottom: 7vw;
    right: 5%;
  }

  .container__topArrow img {
    height: 6vw;
  }
}

@media screen and (min-width: 1200px) {
  #sttmobile {
    display: none;
  }

  .container__topArrow {
    height: 3rem;
    bottom: 9%;
    right: 3%;
  }

  .container__topArrow img {
    height: 5rem;
  }
}
</style>

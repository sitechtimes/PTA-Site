<template>
  <div>
    <h1 class="heading" ref="heading">DONATIONS</h1>
    <h3 class="subh" ref="subh">Bake Sales</h3>
    <p class="text" ref="text">
      Food and drink donations would be much appreciated to help launch bake
      sales during the year. Our students always enjoy these added treats to
      their daily lunch routine.
    </p>
    <p class="text" ref="text2">
      Here is a wish list of items that we would like to provide to our students
      which include : Cookies, Brownies, Plates, Chips, Beverages, Cup Noodles,
      and any other baked goods. <span>(PLEASE NO NUTS)</span>
    </p>
    <p class="text" ref="text3">
      You can sign up for items you wish to bring in on the google form!
    </p>
    <div class="btnCon" ref="btnCon">
      <form
        action="https://docs.google.com/forms/d/e/1FAIpQLSfoRbBX2iCx20Kxcud0IcjT2UhmpjaNxDda78V3BIfN_Mw3Dg/viewform"
        target="_blank"
      >
        <button ref="button" class="btn" id="donate">
    <svg class="svg" id="donSvg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path d="M58.9 42.1c3-6.1 9.6-9.6 16.3-8.7L320 64 564.8 33.4c6.7-.8 13.3 2.7 16.3 8.7l41.7 83.4c9 17.9-.6 39.6-19.8 45.1L439.6 217.3c-13.9 4-28.8-1.9-36.2-14.3L320 64 236.6 203c-7.4 12.4-22.3 18.3-36.2 14.3L37.1 170.6c-19.3-5.5-28.8-27.2-19.8-45.1L58.9 42.1zM321.1 128l54.9 91.4c14.9 24.8 44.6 36.6 72.5 28.6L576 211.6v167c0 22-15 41.2-36.4 46.6l-204.1 51c-10.2 2.6-20.9 2.6-31 0l-204.1-51C79 419.7 64 400.5 64 378.5v-167L191.6 248c27.8 8 57.6-3.8 72.5-28.6L318.9 128h2.2z"/></svg>Donate Item
        </button>
      </form>
      <form
        action="https://docs.google.com/spreadsheets/d/1Pb-NaiamGd8QFYNrhaGD5ARDS-hZbc-1RbByoMdqahY/edit?usp=sharing"
        target="_blank"
      >
        <button ref="button" class="btn" id="donateInv">
          <svg
            class="svg" id="invSvg"
            xmlns="http://www.w3.org/2000/svg"
            height="1em"
            viewBox="0 0 640 512"
          >
            <!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
            <path
              d="M32 0C14.3 0 0 14.3 0 32S14.3 64 32 64H48c8.8 0 16 7.2 16 16V368c0 44.2 35.8 80 80 80h18.7c-1.8 5-2.7 10.4-2.7 16c0 26.5 21.5 48 48 48s48-21.5 48-48c0-5.6-1-11-2.7-16H450.7c-1.8 5-2.7 10.4-2.7 16c0 26.5 21.5 48 48 48s48-21.5 48-48c0-5.6-1-11-2.7-16H608c17.7 0 32-14.3 32-32s-14.3-32-32-32H144c-8.8 0-16-7.2-16-16V80C128 35.8 92.2 0 48 0H32zM192 80V272c0 26.5 21.5 48 48 48H560c26.5 0 48-21.5 48-48V80c0-26.5-21.5-48-48-48H464V176c0 5.9-3.2 11.3-8.5 14.1s-11.5 2.5-16.4-.8L400 163.2l-39.1 26.1c-4.9 3.3-11.2 3.6-16.4 .8s-8.5-8.2-8.5-14.1V32H240c-26.5 0-48 21.5-48 48z"
            /></svg
          >Inventory
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { heading } = this.$refs;
    const { subh } = this.$refs;
    const { text } = this.$refs;
    const { text2 } = this.$refs;
    const { text3 } = this.$refs;
    const { list } = this.$refs;
    const { btnCon } = this.$refs;
    gsap.from(heading, { delay: 0, duration: 1, y: 100, opacity: 0 });
    gsap.from(subh, { delay: 0.4, duration: 1, y: 100, opacity: 0 });
    gsap.from(text, { delay: 0.6, duration: 1, y: 100, opacity: 0 });
    gsap.from(text2, { delay: 0.8, duration: 1, y: 100, opacity: 0 });
    gsap.from(text3, { delay: 1, duration: 1, y: 100, opacity: 0 });
    gsap.from(list, { delay: 1, duration: 1, y: 100, opacity: 0 });
    gsap.from(btnCon, { delay: 1.2, duration: 1, y: 100, opacity: 0 });
  },
};
</script>
<style scoped>
@import url(../assets/base.css);
.btnCon {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  margin: 2% 0 0 8%;
}
.btn {
  padding: 0.7rem 1rem 0.8rem 1rem;
  width: 12rem;
}
#donate {
  margin-right: 2vw;
}
svg {
  margin-right: 10px;
  fill: white;
  margin-top: 0.4rem;
}
#invSvg {
  margin-top: 0.3rem;
}
#donSvg {
  width: 1.4rem;
}
.heading {
  margin: 2% 0 0 8%;
  display: block;
}
.text {
  margin: 1% 0 0 8%;
  width: 80%;
}
span {
  font-weight: bold;
}
.subh {
  margin-top: 1.5rem;
  width: 32vw;
  margin: 2% 0 0 8%;
}
@media screen and (max-width: 1400px) {
  .btnCon {
    margin: 2% 0 0 8%;
  }
  button {
    border-radius: 0.5rem;
    width: 12rem;
    font-size: 1.3rem;
    font-weight: bold;
  }
  #donSvg {
  width: 1rem;
}

  .subh {
    margin-top: 0.8rem;
  }
}

@media screen and (max-width: 1200px) {
  .btnCon {
    margin: 4% 0 0 8%;
  }
  button {
    border-radius: 0.5rem;
    width: 14rem;
    font-size: 1.3rem;

    font-weight: bold;
  }
  .btn {
    width: 10rem;
  }
  .text {
    width: 70%;
    margin-top: 0.8rem;
  }
}
@media screen and (max-width: 992px) {
  .text {
    width: 80%;
    margin-top: 0.8rem;
  }
  .btnCon {
    margin: 4% 0 0 8%;
  }
  button {
    border-radius: 0.5rem;
    width: 12rem;
    font-size: 1.2rem;

    font-weight: bold;
  }
  svg {
    margin-right: 8px;
  }
}

@media screen and (max-width: 768px) {
}

@media screen and (max-width: 576px) {
  .btnCon {
    margin: 4% 0 0 8%;
  }
  button {
    border-radius: 0.4rem;
    width: 10rem;
    font-size: 1rem;
  }
  .btn {
    width: 9rem;
  }
  .text {
    width: 80%;
    margin-top: 0.8rem;
  }
}
@media only screen and (max-width: 450px) {
  .subh {
    width: 80%;
  }
  .btnCon {
    margin: 7% 0 0 8%;
  }
  button {
    border-radius: 0.4rem;
    width: 10rem;
    font-size: 1rem;
  }
}
@media only screen and (max-width: 356px) {
  .btnCon {
    margin: 4% 0 0 8%;
    flex-direction: column;
  }
  button {
    border-radius: 0.4rem;
    width: 8rem;
    font-size: 0.9rem;
  }
  #donate {
    margin-bottom: 2vw;
  }
}
</style>

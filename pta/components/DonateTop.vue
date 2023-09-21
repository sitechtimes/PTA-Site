<template>

          <div>
            <h1 class="heading" ref="heading">DONATIONS</h1>
              <h3 class="subh" ref="subh">Bake Sales</h3>
                <p ref="text">Food and drink donations would be much appreciated to help launch bake sales during the year. Our students always enjoy these added treats to their daily lunch routine. </p>
                <p ref="text2">Attached is a wish list of items that we would like to provide to our students which include :</p>
                <ul ref="list" class="list">
                    <li>Cookies </li>  
                    <li>Brownies  </li>
                    <li>Plates  </li>
                    <li>Chips </li>
                    <li>Beverages  </li>
                    <li>Cup Noodles  </li> 
                    <li>Any other baked goods</li>
                    <li><span>(PLEASE NO NUTS)</span> </li>
                </ul>
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
    const { list } = this.$refs;
        gsap.from(heading, { delay: 0.0, duration: 1, y: 100, opacity: 0 });
    gsap.from(subh, { delay: 0.5, duration: 1, y: 100, opacity: 0 });
    gsap.from(text, { delay: 0.8, duration: 1, y: 100, opacity: 0 });
    gsap.from(text2, { delay: 1, duration: 1, y: 100, opacity: 0 });
    gsap.from(list, { delay: 1.2, duration: 1, y: 100, opacity: 0 });

  }

};
</script>
<style scoped>
@import url(../assets/base.css);
.heading{
margin: 2% 0 0 8%;
}
.list{
    margin: 1% 0 0 8%;
    font-family: var(  --font-text);

}
li{
  font-size: 1.7rem;
  margin-top: 0.5rem;
}

p {
  font-size: 1.7rem;
margin: 1% 0 0 8%;
width: 66%;
font-family: var(  --font-text);
}
span{
  font-weight: bold;
}
.subh {
  margin-top: 1.5rem;
  width: 32vw;
margin: 2% 0 0 8%;
    margin-top: 1.5rem;
}


</style>
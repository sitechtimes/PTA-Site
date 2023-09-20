<template>
<div>
     <div id="gradient"></div>
                <h1 class="heading">DONATIONS</h1>
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
                <h3 class="subh">Monetary Donations</h3>
                <p>Monetary donations are always graciously accepted throughout the school year. If you have already donated, we thank you for your generosity and support.</p>
                <p>To donate, please bring the completed form and donation to Ms. Barbara Malenfant’s office, Room 117</p>
</div>
</template>
<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { subh } = this.$refs;
    const { text } = this.$refs;
    const { list } = this.$refs;
        const { text2 } = this.$refs;
    gsap.from(".heading", { duration: 1, y: 100, opacity: 0 });
    gsap.from(subh, { delay: 0.5, duration: 1, y: 100, opacity: 0 });
    gsap.from(text, { delay: 0.8, duration: 1, y: 100, opacity: 0 });
    gsap.from(text2, { delay: 1, duration: 1, y: 100, opacity: 0 });
    gsap.from(list, { delay: 1.2, duration: 1, y: 100, opacity: 0 });
  },
};
</script>
<style scoped>
@import url(../assets/base.css);
.list{
    margin: 1% 0 0 8%;
    font-family: var(  --font-text);

}
li{
  font-size: 1.5rem;
  margin-top: 0.5rem;
}
span{
    font-weight: bold;
}
p {
  font-size: 1.5vw;
margin: 1% 0 0 8%;
width: 66%;
font-family: var(  --font-text);
}
.heading{
margin: 2% 0 0 8%;
}
.subh {
  margin-top: 1.5rem;
  width: 32vw;
margin: 2% 0 0 8%;
    margin-top: 1.5rem;
}
#gradient {
  width: 100%;
  height: 80vw;
  position: absolute;
  top: 0;
  left: 0;
  padding: 0;
  background: var(--bg-gradient);
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
  align-items: center;
  overflow-x: hidden;
  z-index: -1;
  overflow-x: hidden;
}


</style>
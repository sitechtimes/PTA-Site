<template>

          <div id="monetary" >
                <h3 class="subh" id="sub" ref="subh2">Monetary Donations</h3>
                <p ref="text3">Monetary donations are always graciously accepted throughout the school year. If you have already donated, we thank you for your generosity and support.</p>
                <p ref="text4">To donate, please bring the completed form and donation to Ms. Barbara Malenfant’s office, Room 117</p>
</div>
                

</template>

<script>
import { gsap } from "gsap";
export default {
  mounted() {
    const { list } = this.$refs;
    const { subh2 } = this.$refs;
    const { text3 } = this.$refs;
    const { text4 } = this.$refs;

    gsap.from(list, { delay: 1.2, duration: 1, y: 100, opacity: 0 });
    gsap.from(subh2, { delay: 1.4, duration: 1, y: 100, opacity: 0 });
    gsap.from(text3, { delay: 1.6, duration: 1, y: 100, opacity: 0 });
    gsap.from(text4, { delay: 1.8, duration: 1, y: 100, opacity: 0 });

  }

};
</script>
<style scoped>
@import url(../assets/base.css);

#monetary{
  margin-top: 15rem;
  margin-bottom: 10rem;
}

p {
font-size: 1.7rem;
margin: 1% 0 0 8%;
width: 66%;
font-family: var(  --font-text);
}

.subh {
  margin-top: 1.5rem;
  width: 32vw;
margin: 2% 0 0 8%;
    margin-top: 1.5rem;
}
@media screen and (max-width: 1400px){

#monetary{
  margin-top: 8rem;
}
.subh{
  margin-top: 0.8rem;
}
p{
  font-size: 1.5rem;
}

}

@media screen and (max-width: 1200px) {
  #monetary{
  margin-top: 5rem;
}
p{
  font-size: 1.4rem;
    width: 70%;
    margin-top: 0.8rem;
}
.subh{
  width: 70%;
}
}

@media screen and (max-width: 992px) {
}

@media screen and (max-width: 768px) {

}

@media screen and (max-width: 576px) {
  #monetary{
  margin-top: 2.5rem;
}
p{
  font-size: 1.1rem;
    width: 80%;
        margin-top: 0.8rem;
}
li{
  margin-top: 0.2rem;
  font-size: 1.1rem;
}
}

@media only screen and (max-width: 450px) {
  .subh{
    width: 80%;
  }
  #monetary{  margin-top: 3rem;
  margin-bottom: 5rem;
}
}
@media only screen and (max-width: 356px) {

}

</style> 
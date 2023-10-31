<template>
<div>
    <h1 class="heading">GALLERY</h1>
        <div class="gallery">
        <div class="polaroid">
            <div id="picture"></div>
            <a class="name" href="">test</a>
        </div>
        <div class="polaroid">
            <div id="picture"></div>
            <a class="name" href="">test</a>
        </div>
                <div
          v-for="polaroid in polaroids"
          class="uniqEvent">
          <div class="polaroid">
            <div id="picture"><img :src="photo.image" alt="{{ polaroid.title }}"></div>
            <a class="name" href="{{ polaroid.link }}">{{ polaroid.title }}</a>
        </div>
     
        </div>
    
    </div>
</div>
</template>
<style scoped>

.name {
  font-family: "Kumbh Sans", sans serif;
  font-style: normal;
  color: #483221;
  text-align: center;
  font-size: 1.2rem;
  display: block;
  font-weight: bolder;
  text-align: center;
  margin-top: 3rem;
}
.gallery {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr ;
  grid-gap: 4rem;
  margin: 11rem;
  margin-top: 4rem;
  justify-items: center;
  grid-template-rows: auto;
  padding-bottom: 0rem;
}
.polaroid {
  background-color: white;
  height: 26rem;
  width: 18rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: 0.3s;
}
.polaroid:hover {
  transform: scale(1.02);
}
#picture {
  height: 14rem;
  width: 14rem;
  margin: 3rem;
  margin-bottom: 0;
  margin-top: 0;
  z-index: 1;
  background-color: rgb(194, 194, 194);
}

</style>
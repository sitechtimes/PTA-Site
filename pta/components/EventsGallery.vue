<template>
    <div>
        <h1 class="heading">EVENTS GALLERY</h1>
        <div class="gallerygrid">
            <div class="polaroid"></div>

        </div>

    </div>
</template>
<style scoped>
@import "../assets/base.css";

.gallerygrid {
    display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr ;
  overflow: hidden;
  grid-column-gap: 10%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
.polaroid{
border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 2vw;
  width: 18vw;
  height: 20vw;
  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
}
</style>
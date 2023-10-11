<template>
  <!-- <div class="space"> -->
  <div class="container__footer">
    <div class="sections">
        <div class="left">

        <img
          class="logo"
          src="../components/icons/NavBar-Icons/pta-logo.png"
          alt=""
        />
            <div class="pages">
              

  </div>

        </div>
        <div class="mid">

        </div>
        <div class="right">

        </div>
    </div>
  </div>
  <!-- </div> -->
</template>

<style scoped>
.pages{
    display: flex;
    flex-direction: row;
    font-family: "Kumbh Sans" ;
}
img{
    width: 35%;
}
.left{
    display: flex;
    flex-direction: column;
}
.sections {
    display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  overflow: hidden;
margin: auto;
  grid-column-gap: 20px;
  margin-top: 5px;
  width: 80%;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 30%;
}
</style>

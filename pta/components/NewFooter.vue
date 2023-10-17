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
               <NuxtLink
               class="link"
                 to="/"
                  @click="(page = 'index'), underline()"
                 v-bind:style="({ animation: fadeIn })"
        >  
          Home</NuxtLink
        >
        |
                       <NuxtLink
               class="link"
                 to="/Events"
                  @click="(page = 'index'), underline()"
                 v-bind:style="({ animation: fadeIn })"
        >  
          Events </NuxtLink
        >
        |
                               <NuxtLink
               class="link"
                 to="/ContactUs"
                  @click="(page = 'index'), underline()"
                 v-bind:style="({ animation: fadeIn })"
        >  
          Contact Us </NuxtLink
        >
        |
                               <NuxtLink
               class="link"
                 to="/Donate"
                  @click="(page = 'index'), underline()"
                 v-bind:style="({ animation: fadeIn })"
        >  
         Donate </NuxtLink
        >

  </div>
        <h3>SIT PTA @2023</h3>
        </div>
        <div class="mid">
            <div class="info">
                <div class="email">
<svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M48 64C21.5 64 0 85.5 0 112c0 15.1 7.1 29.3 19.2 38.4L236.8 313.6c11.4 8.5 27 8.5 38.4 0L492.8 150.4c12.1-9.1 19.2-23.3 19.2-38.4c0-26.5-21.5-48-48-48H48zM0 176V384c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V176L294.4 339.2c-22.8 17.1-54 17.1-76.8 0L0 176z"/></svg>
                    <h2>sitechpta@gmail.com</h2>
                </div>
                <div class="address">
                    <svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 384 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M215.7 499.2C267 435 384 279.4 384 192C384 86 298 0 192 0S0 86 0 192c0 87.4 117 243 168.3 307.2c12.3 15.3 35.1 15.3 47.4 0zM192 128a64 64 0 1 1 0 128 64 64 0 1 1 0-128z"/></svg>
                    <h2>485 Clawson Street, Staten Island, NY 10306</h2>
                </div>
            </div>
            <div class="icons">
                <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H384c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64zm297.1 84L257.3 234.6 379.4 396H283.8L209 298.1 123.3 396H75.8l111-126.9L69.7 116h98l67.7 89.5L313.6 116h47.5zM323.3 367.6L153.4 142.9H125.1L296.9 367.6h26.3z"/></svg>
                <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M224,202.66A53.34,53.34,0,1,0,277.36,256,53.38,53.38,0,0,0,224,202.66Zm124.71-41a54,54,0,0,0-30.41-30.41c-21-8.29-71-6.43-94.3-6.43s-73.25-1.93-94.31,6.43a54,54,0,0,0-30.41,30.41c-8.28,21-6.43,71.05-6.43,94.33S91,329.26,99.32,350.33a54,54,0,0,0,30.41,30.41c21,8.29,71,6.43,94.31,6.43s73.24,1.93,94.3-6.43a54,54,0,0,0,30.41-30.41c8.35-21,6.43-71.05,6.43-94.33S357.1,182.74,348.75,161.67ZM224,338a82,82,0,1,1,82-82A81.9,81.9,0,0,1,224,338Zm85.38-148.3a19.14,19.14,0,1,1,19.13-19.14A19.1,19.1,0,0,1,309.42,189.74ZM400,32H48A48,48,0,0,0,0,80V432a48,48,0,0,0,48,48H400a48,48,0,0,0,48-48V80A48,48,0,0,0,400,32ZM382.88,322c-1.29,25.63-7.14,48.34-25.85,67s-41.4,24.63-67,25.85c-26.41,1.49-105.59,1.49-132,0-25.63-1.29-48.26-7.15-67-25.85s-24.63-41.42-25.85-67c-1.49-26.42-1.49-105.61,0-132,1.29-25.63,7.07-48.34,25.85-67s41.47-24.56,67-25.78c26.41-1.49,105.59-1.49,132,0,25.63,1.29,48.33,7.15,67,25.85s24.63,41.42,25.85,67.05C384.37,216.44,384.37,295.56,382.88,322Z"/></svg>
                <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M400 32H48A48 48 0 0 0 0 80v352a48 48 0 0 0 48 48h137.25V327.69h-63V256h63v-54.64c0-62.15 37-96.48 93.67-96.48 27.14 0 55.52 4.84 55.52 4.84v61h-31.27c-30.81 0-40.42 19.12-40.42 38.73V256h68.78l-11 71.69h-57.78V480H400a48 48 0 0 0 48-48V80a48 48 0 0 0-48-48z"/></svg>
            </div>
        </div>
        <div class="right">
            <h2 class="about">About Us</h2>
            <h3 class="mission">The mission of Staten Island Tech’s PTA is to support our school through advocacy, volunteerism and fundraising. From our bake sales to our annual Spring Gala, we work diligently to raise money in order to financially support our school’s needs such as online and software services, facility upgrades and social events / celebrations.</h3>
 <button ref="button">Donate Now!</button>
        </div>
    </div>
  </div>
  <!-- </div> -->
</template>

<style scoped>
.hand{
    fill: white;
}
button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 33%;
      font-size: 1.2rem;
    margin-top: 2rem;
    padding: 6px;
      font-weight: 450;
}
button:hover{
  cursor: pointer; 

}
.mission{
    margin-top: 0;
    width: 95%;
    margin: 0;
        margin-top: 0.5rem;
}
.about{
    font-weight: bold;
    font-size: 1.2rem;
    margin: 0;

}
.container__footer{
    margin-bottom: 4rem;
}
svg{
    fill: #483221;
            margin-top: 1rem;
            margin-right: 0.5rem;
}
.email{
    display: flex;
            margin-top: 1.5rem;
    flex-direction: row;
}
.address{
        display: flex;
    margin-top: 0.5rem;
    flex-direction: row;
}
.mid{
    display: flex;
    flex-direction: column;
}
h3{
        font-family: "Kumbh Sans" ;
        color: #483221;
        font-size: 1rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0.5rem;
}
h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 1rem;
        font-size: 1.2rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
}
.link{
        color: #483221;
        text-decoration: none;
        font-size: 1.2rem;
        margin-right: 0.5rem;
        margin-left: 0.5rem;
}
.pages{
    display: flex;
    flex-direction: row;
    font-family: "Kumbh Sans" ;
    margin-top: 2rem;
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
  grid-column-gap: 10px;
  margin-top: 5px;
  width: 85%;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 35%;
}

@media screen and (max-width: 1400px) {
    .container__footer{
    margin-bottom: 3.4rem;
}
.sections{
    width: 90%;

}
.link{
    font-size: 1.1rem;
}

h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 0.8rem;
        font-size: 1.1rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
                width: 85%;
}
svg{
    margin-top: 0.8rem;
}
.mission{
    margin-top: 0;
    width: 90%;
    margin: 0;
        margin-top: 0.4rem;
        font-size: 0.9rem;
}
.about{
    font-weight: bold;
    font-size: 1.1rem;
    margin: 0;

}

button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 32%;
      font-size: 1rem;
    margin-top: 1.4rem;
    padding: 7px;
      font-weight: 450;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 35%;
}
}

@media screen and (max-width: 1200px) {
    .container__footer{
    margin-bottom: 3.5rem;
}
.sections{
    width: 95%;
}
.link{
    font-size: 1rem;
}
h3{
    font-size: 0.8rem;
    margin-top: 0.5rem;
}
h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 0.9rem;
        font-size: 0.9rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
}
svg{
    margin-top: 0.8rem;
    width: 1.5rem;
}
.mission{
    margin-top: 0;
    width: 95%;
    margin: 0;
        margin-top: 0.4rem;
        font-size: 0.9rem;
}
.about{
    font-weight: bold;
    font-size: 1.1rem;
    margin: 0;

}
button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 32%;
      font-size: 1rem;
    margin-top: 1.2rem;
    padding: 7px;
      font-weight: 450;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 35%;
}
}
@media screen and (max-width: 992px) {
  .link{
    font-size: 1rem;
    
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 5px;
  margin-top: 5px;
  width: 50%;
}
    .container__footer{
    margin-bottom: 3.5rem;
}
.sections{
    width: 90%;

}
.link{
    font-size: 1.1rem;
}

h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 0.8rem;
        font-size: 1.1rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
}
svg{
    margin-top: 0.8rem;
}
.mission{
    margin-top: 0;
    width: 90%;
    margin: 0;
        margin-top: 0.4rem;
        font-size: 0.9rem;
}
.about{
    font-weight: bold;
    font-size: 1.1rem;
    margin: 0;

}

button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 32%;
      font-size: 1rem;
    margin-top: 1.4rem;
    padding: 7px;
      font-weight: 450;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 35%;
}
}

@media screen and (max-width: 1200px) {
    .container__footer{
    margin-bottom: 3.5rem;
}
.sections{
    width: 95%;
}
.link{
    font-size: 0.8rem;
    margin-left: 5px;
    margin-right: 4px;
}
h3{
    font-size: 0.8rem;
    margin-top: 0.5rem;
}
h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 0.9rem;
        font-size: 0.9rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
}
svg{
    margin-top: 0.8rem;
    width: 1.5rem;
}
.mission{
    margin-top: 0;
    width: 98%;
    margin: 0;
        margin-top: 0.4rem;
        font-size: 0.8rem;
}
.about{
    font-weight: bold;
    font-size: 1.1rem;
    margin: 0;

}
button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 45%;
      font-size: 0.9rem;
    margin-top: 1.2rem;
    padding: 6px;
      font-weight: 450;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 5px;
  width: 50%;
}
}
@media only screen and (max-width: 768px) {
    .email{
        margin-top: 0;
    }
    .container__footer{
    margin-bottom: 3.5rem;
}
.sections{
    width: 95%;
}
.link{
    font-size: 0.7rem;
    margin-left: 4px;
    margin-right: 4px;
}
h3{
    font-size: 0.7rem;
    margin-top: 0.4rem;
    margin-left: 4px;
}
h2{
     font-family: "Kumbh Sans" ;
        color: #483221;
        margin-top: 0.95rem;
        font-size: 0.9rem;
        margin-right: 0;
        font-weight: 400;
        margin-left: 0rem;
}
svg{
    margin-top: 0.8rem;
    width: 1.4rem;
}
.mission{
    margin-top: 0;
    width: 96%;
    margin: 0;
        margin-top: 0.3rem;
        font-size: 0.725rem;
}
.about{
    font-weight: bold;
    font-size: 1.1rem;
    margin: 0;

}
button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 45%;
      font-size: 0.9rem;
    margin-top: 1.2rem;
    padding: 6px;
      font-weight: 450;
}
.icons {
  grid-template-columns: 1fr 1fr 1fr ;
  overflow: hidden;
  display: grid;
  grid-column-gap: 0px;
  margin-top: 4px;
  width: 50%;
}

}
@media only screen and (max-width: 576px) {
.sections {
    display: flex;
flex-direction: column;
  overflow: hidden;
margin: auto;
  grid-column-gap: 10px;
  margin-top: 5px;
  width: 85%;
}
    .container__footer{
    margin-bottom: 2.5rem;
}
.pages{
    margin-top: 1rem;
}
img{
    width: 30%;
}
.link{
    font-size: .8rem;
    margin-top: 2px;
    font-weight: 500;
}
h2{
    margin-top: 4px;
    width: 100%;
}
.icons{
margin-bottom: 1rem;
margin-top: 0.5rem;
}
svg{
    margin-top: 0rem;
    width: 1.25rem;
}
.address{
        display: flex;
    margin-top: 0.8rem;
    flex-direction: row;
}
.email{
    margin-top: .8rem;
}
.mission{
    font-size: .8rem;
}
button{
      fill: white;
      color: white;
      background:#483221 ;
        font-family: "Kumbh Sans" ;
      border-radius: 0.5rem; 
      border: none;
      width: 40%;
      font-size: 0.9rem;
    margin-top: 1.2rem;
    padding: 6px;
      font-weight: 450;
}
}
@media only screen and (max-width: 375px){
    h2{
        margin-top: 4px;
    }
    svg{
        margin-top: 2px;
        width: 1.3rem;
    }
}
</style>

<template>
    <div class="resources">
        <h2 class="heading">RESOURCES</h2>
         <!-- <div class="resourcegrid" v-for="resource in resources">
            <div class="resource">
                <img :src="resource.image" alt="photo img">
                <div class="info">
                    <h3 class="name">{{resource.name}} </h3>
                    <h4 class="description">{{resource.description}}  </h4>
                   <a target="_blank" :href="resource.link" ><button class="button">Read More</button></a> 
                </div>
            </div>
            </div> -->
        <h2 id="heading" class="heading">RESOURCES</h2>
        <div id="grid" class="resourcegrid">
            <div class=" resource">
                <img src="https://3.files.edl.io/fd75/20/04/09/191319-2af8eea0-9bd2-4795-8791-640f550a5c8f.png" alt="">
                <div class="info">
                    <h3 class="name">SITHS Automated Telephone 
                    Directory </h3>
                    <h4 class="description">Contact Staten Island Technical High School.  </h4>
                   <a target="_blank" href="https://www.siths.org/apps/pages/index.jsp?uREC_ID=1555040&type=d&pREC_ID=1680913"><button class="button">Read More</button></a> 
                </div>

            </div>
            <div class="resource"> 
                <img src="https://www.stcroixprep.org/wp-content/uploads/2019/12/Naviance-Logo-300x300.png" alt="">
                <div class="info">
                    <h3 class="name">Naviance </h3>
                    <h4 class="description">Parents can track secondary goals and success.  </h4>
                    
                    <a target="_blank" href="https://id.naviance.com/"><button class="button">Read More</button></a>
                </div>

            </div>

                        <div class="resource">
                <img src="https://nycaieroundtable.org/wp-content/uploads/2022/02/nyc-doe-logo.jpg" alt="">
                <div class="info">
                    <h3 class="name">NYCDOE Websites </h3>
                    <h4 class="description">Keep track of student documents 
and official city calendars   </h4>
<a target="_blank" href="https://www.schools.nyc.gov/">  <button class="button">Read More</button></a>
                </div>

            </div>

             <div class="resource">
                <img src="./icons/NavBar-Icons/pta-logo.png" alt="">
                <div class="info">
                    <h3 class="name">SITHS PTA By-laws</h3>
                    <h4 class="description">Read more about the PTA</h4>
<a target="_blank" href="https://docs.google.com/document/d/1gNyKPMDOUxeW2AadJFuOXtla3jd_bzjw/edit?usp=sharing&ouid=109431569121511580485&rtpof=true&sd=true">  <button class="button">Read More</button></a>
                </div>

            </div>

        </div>

    </div>
</template>
<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
    methods: {
    scrollActivities() {
      gsap.to({
        ScrollTrigger: {
          trigger: "#heading",
          start: "center center",
          end: "bottom top",
        },
      });
    },
  },
    mounted() {
    gsap.from("#heading", {
      scrollTrigger: "#heading",
      delay: .6,
      duration: 1,
x: -600,
      opacity: 0,
    });
    gsap.from("#grid", {
      scrollTrigger: "#grid",
      delay: .8,
      duration: 1,
x: -600,
      opacity: 0,
    });
  },
}
</script>
<style scoped>
@import "../assets/base.css";
a{
    text-decoration: none;
}
h2{
    margin-top: 0;
}
.heading{
  margin: 0% 0 0 6.5%;
}
.resourcegrid {
    display: grid;
  grid-template-columns: 1fr 1fr;
  overflow: hidden;
  grid-column-gap: 10%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 2vw;
  border-radius: 1vw;
  width: 28.5vw;
  height: 13.5vw;
  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
}
.info{
    display: flex;
    flex-direction: column;
    width: 60%;
    margin-left: 5%;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 1.3rem; width: 60%;
padding: 0.4rem;
border-radius: 2rem;
font-weight: 500;
border: none;
margin-top: 1rem;
margin-bottom: 1.5rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
img{
    width: 30%;
    margin: auto;
}
.name {
  font-size: 1.7rem;
  color: var(--text-color);
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  margin-bottom: 0;
}
.description {
    margin-top: 0.7rem;
  font-size: 1.5rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
}
@media screen and (max-width: 1400px){
    
.heading{
    margin-top: 1.3rem;
}
.resourcegrid {
    display: grid;
  grid-template-columns: 1fr 1fr;
  overflow: hidden;
  grid-column-gap: 10%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 2vw;
  border-radius: 1vw;
  width: 30vw;
  height: 15vw;
  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
}
.info{
    display: flex;
    flex-direction: column;
    width: 60%;
    margin-left: 5%;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 1.15rem; width: 60%;
padding: 0.35rem;
border-radius: 2rem;
font-weight: 500;
border: none;
margin-top: 0.6rem;
margin-bottom: 1.5rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
img{
    width: 30%;
    margin: auto;
}
.name {
  font-size: 1.5rem;
  color: var(--text-color);
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  margin-bottom: 0;
  margin-top: 1.2rem;
}
.description {
    margin-top: 0.4rem;
  font-size: 1.2rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
}
}
@media screen and (max-width: 1200px){
    .heading{
    margin-top: 1.3rem;
}
.resourcegrid {
    display: grid;
  grid-template-columns: 1fr 1fr;
  overflow: hidden;
  grid-column-gap: 5%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 2vw;
  border-radius: 1vw;
  width: 32vw;
  height: 18vw;
  box-shadow: 4px 4px 4px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
}
.info{
    display: flex;
    flex-direction: column;
    width: 60%;
    margin-left: 5%;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 1.1rem; width: 65%;
padding: 0.3rem;
border-radius: 2rem;
font-weight: 400;
border: none;
margin-top: 0.6rem;
margin-bottom: 1.5rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
img{
    width: 30%;
    margin: auto;
}
.name {
  font-size: 1.25rem;
  color: var(--text-color);
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  margin-bottom: 0;
  margin-top: 1.2rem;
}
.description {
    margin-top: 0.3rem;
  font-size: 1.1rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
}
}
@media screen and (max-width: 992px) {
 .heading{
    margin-top: 1.3rem;
}
.resourcegrid {
    display: grid;
  grid-template-columns: 1fr 1fr;
  overflow: hidden;
  grid-column-gap: 3%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 4vw;
  border-radius: 1vw;
  width: 33vw;
  height: 17vw;
  box-shadow: 3px 3px 3px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
}
.info{
    display: flex;
    flex-direction: column;
    width: 60%;
    margin-left: 5%;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 0.8rem; width: 65%;
padding: 0.25rem;
border-radius: 2rem;
font-weight: 400;
border: none;
margin-top: 0.4rem;
margin-bottom: 1.3rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
img{
    width: 25%;
    margin: auto;
}
.name {
  font-size: 0.9rem;
  color: var(--text-color);
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  margin-bottom: 0;
  margin-top: 1rem;
}
.description {
    margin-top: 0.2rem;
  font-size: 0.8rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
}
}
@media only screen and (max-width: 768px) {
    .resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 4vw;
  border-radius: 1vw;
  width: 33vw;
  height: 17vw;
  box-shadow: 2px 2px 2px 0px rgba(0, 0, 0, 0.178);
  display: flex;
  flex-direction: row;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 0.7rem; width: 65%;
padding: 0.2rem;
border-radius: 2rem;
font-weight: 300;
border: none;
margin-top: 0.5rem;
margin-bottom: 1.3rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
.description {
    margin-top: 0.2rem;
  font-size: 0.75rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
  line-height: 1;
}
}
@media only screen and (max-width: 576px) {
  .heading{
        margin-left: 8vw;
  }
  .name {
  font-size: 0.95rem;
  color: var(--text-color);
  font-family: "Kumbh Sans", san serif;
  font-weight: 800;
  margin-bottom: 0;
  margin-top: 1rem;
}
    img{
    width: 25%;
    margin: auto;
}
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 6vw;
  border-radius: 2vw;
  width: 75vw;
  height: 33vw;
  box-shadow: 2px 2px 2px 0px rgba(0, 0, 0, 0.178);
  display: flex;
  flex-direction: row;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 0.85rem; width: 60%;
padding: 0.2rem;
border-radius: 2rem;
font-weight: 550;
border: none;
margin-top: 0.8rem;
transition: 0.3s;
}
.button:hover{
    cursor: pointer;
    opacity: 0.6;
}
.description {
  width: 95%;
    margin-top: 0.3rem;
  font-size: 0.85rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
  line-height: 1;
}
.resourcegrid {
    display: grid;
  grid-template-columns:  1fr;
  overflow: hidden;
  grid-column-gap: 3%;
  width: 85%;
  padding-top: 3rem;
padding-bottom: 5rem;
  margin: auto;
}
}
@media only screen and (max-width: 420px){
.resource{
    border: 1px #D6D6D6 solid;
  background-color: white;
  padding: 0vw 3vw 0vw 3vw;
  margin-bottom: 6vw;
  border-radius: 2vw;
  width: 74vw;
  height: 33vw;
  box-shadow: 2px 2px 2px 0px rgba(0, 0, 0, 0.178);
  display: flex;
  flex-direction: row;
}
.button{
background-color: #C9B23A;
color: white;
font-family: "Kumbh Sans", san serif;
font-size: 0.80rem; width: 60%;
padding: 0.2rem;
border-radius: 2rem;
font-weight: 550;
border: none;
margin-top: 0.5rem;
transition: 0.3s;
}
.resourcegrid {
  margin-top: 0;
  padding-top: 2rem;
padding-bottom: 2.5rem;
  margin: auto;
}
.description {
  width: 90%;
    margin-top: 0.3rem;
  font-size: 0.82rem;
  color: var(--text-color);
  font-family: "Karla", sans serif;
  font-weight: 400;
  margin-bottom: 0;
  line-height: 1;
}
}
</style>
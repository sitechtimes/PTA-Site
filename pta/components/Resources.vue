<template>
    <div class="resources">
        <h2 class="heading">RESOURCES</h2>
        <div class="resourcegrid">
            <div class=" resource">
                <img src="https://3.files.edl.io/fd75/20/04/09/191319-2af8eea0-9bd2-4795-8791-640f550a5c8f.png" alt="">
                <div class="info">
                    <h3 class="name">SITHS Automated Telephone 
Directory </h3>
                    <h4 class="description">Contact Staten Island Technical 
High School.  </h4>
                    <button class="button">Read More</button>
                </div>

            </div>
            <div class="resource">
                <img src="https://www.stcroixprep.org/wp-content/uploads/2019/12/Naviance-Logo-300x300.png" alt="">
                <div class="info">
                    <h3 class="name">Naviance </h3>
                    <h4 class="description">Parents can track achievement to post- secondary goals and success.  </h4>
                    <button class="button">Read More</button>
                </div>

            </div>

                        <div class="resource">
                <img src="https://nycaieroundtable.org/wp-content/uploads/2022/02/nyc-doe-logo.jpg" alt="">
                <div class="info">
                    <h3 class="name">NYCDOE Websites </h3>
                    <h4 class="description">Keep track of student documents 
and official city calendars   </h4>
                    <button class="button">Read More</button>
                </div>

            </div>

        </div>

    </div>
</template>
<script>
</script>
<style scoped>
@import "../assets/base.css";
h2{
    margin-top: 0;
}
.heading{
    margin-top: 2rem;
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
</style>
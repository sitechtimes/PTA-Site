<template>
    <section id="section__MiddleSection">
        <div class="information">
            <div class="activities">
                  <h2>ACTIVITIES</h2>
       <h3>The SITHS PTA is a group of parents and faculty/staff members who work together to provide our children with resources and activities to make their school experience the best ever!</h3>
            </div>
     <div class="minutes">       <h2> MEETING MINUTES</h2>
<h3>Link to May 2023 Meeting Minutes</h3></div>

        </div>
        <div class="gallery">
            <PhotoGallery />
        </div>
    </section>
</template>

<style scoped>
.information{
margin-left: 5%;

}
h2{
    font-weight: bold;
    font-family: 'Kumbh Sans', sans-serif;
}
h3{
    font-weight: 500;
    width: 80%;
    font-family: 'Karla', sans-serif;
}
.minutes{
    margin-top: 5rem;
}
#section__MiddleSection {
    margin-top: 5rem;
    display: flex;
    flex-direction: row;
    width: 100vw;
    padding: 1rem;
    align-items: center;
    justify-content: center;
}

.information {
    width: 50vw;
    z-index: 2;
}

.gallery {
    margin-right: 3rem;
}

@media screen and (max-width: 576px) {
    #section__MiddleSection {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

}

@media screen and (max-width: 1024px) {
    #section__MiddleSection {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
}
</style>
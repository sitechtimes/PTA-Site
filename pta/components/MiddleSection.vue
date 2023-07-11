<template>
    <section id="section__MiddleSection">
        <div class="information">
            <p>pta info</p>
        </div>
        <div class="gallery">
            <PhotoGallery />
        </div>
    </section>
</template>

<style scoped>
#section__MiddleSection {
    display: flex;
    flex-direction: row;
    width: 100vw;
    padding: 1rem;
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
</style>
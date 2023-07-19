<template>
    <div class="container__ScrollDown">
        <img src="/ScrollDown.svg" alt="scroll to top button" @click="scrollDown" />
    </div>
</template>
  
<script>
export default {
    methods: {
        scrollDown() {
            const element = document.getElementById("section__MiddleSection");
            element.scrollIntoView({ behavior: "smooth" });
        },
    },
};
</script>
  
<style scoped>

.container__ScrollDown{
    width: 100vw;
    display: flex;
    flex-direction: row;
    align-content: center;
    justify-content: center;
}

.container__ScrollDown img {
    width: 4rem;
    position: absolute;
    display: block;
    bottom: 5vh;
    margin: auto;
    opacity: .8;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    translate: (50%);
    -webkit-animation: scrolling 2s infinite;
    animation: scrolling 2s infinite;
    box-sizing: border-box;
    translate: (50);
}

@-webkit-keyframes scrolling {
    0% {
        -webkit-transform: rotate(-45deg) translate(0, 0);
        opacity: 0;
    }

    50% {
        opacity: 1;
    }

    100% {
        -webkit-transform: rotate(-45deg) translate(-20px, 20px);
        opacity: 0;
    }
}

</style>
<template>
    <div id="homeTopCon">
        <div id="homeTopText">
            <h2 id="pta">Parent Teacher Association @</h2>
            <h1 id="siths">STATEN ISLAND <br/>TECHNICAL <br/>HIGH SCHOOL</h1>
            <p id="address">485 Clawson Street, Staten Island, NY 10306</p>
        </div>
    </div>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Bayon&family=Karla&family=Kumbh+Sans:wght@800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Bubblegum+Sans&family=Cute+Font&family=Kumbh+Sans&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Bubblegum+Sans&family=Cute+Font&family=Karla:wght@500&family=Kumbh+Sans&display=swap');

body{
    overflow-x: hidden;
}

#homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 55vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    top: 15vw;
    left: 7vw;
}
#address{
    margin: 0%;
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.48px;
    font-size: 1.27vw;
}
#siths{
    color: var(--text-color);
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    margin: 0%;
    font-size: 5vw;
    font-style: normal;
    font-weight: 800;
    line-height: 129.164%;
    letter-spacing: 4.6px;
    margin-bottom: .2vw;
}
#pta{
    margin: 0%;
    color: #483221;
    font-family: Kumbh Sans;
    font-size: 2.1vw;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.48px;
    margin-bottom: .4vw;
}

@media screen and (min-width: 480px) {

}
</style>
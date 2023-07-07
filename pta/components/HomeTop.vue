<template>
    <div id="homeTopCon">
        <meta name="viewport" content="width=device-width, initial-scale=1" />
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

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (max-width: 600px) {
    #homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 220vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    left: 50%;
    transform: translate(-50%, 40vw);
    white-space: nowrap;
}
#address{
    margin: 0%;
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.047vw;
    font-size: 3.77vw;
}
#siths{
    color: var(--text-color);
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    margin: 0%;
    font-size: 8.5vw;
    font-style: normal;
    font-weight: 800;
    line-height: 129.164%;
    letter-spacing: 0.449vw;
    margin-bottom: 4vw;
}
#pta{
    margin: 0%;
    color: #483221;
    font-family: Kumbh Sans;
    font-size: 4.6vw;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.047vw;
    margin-bottom: 3vw;
}
}

@media only screen and (min-width: 601px) {
    #homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 220vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    left: 50%;
    transform: translate(-50%, 40vw);
    white-space: nowrap;
}
#address{
    margin: 0%;
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.047vw;
    font-size: 3.77vw;
}
#siths{
    color: var(--text-color);
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    margin: 0%;
    font-size: 8.5vw;
    font-style: normal;
    font-weight: 800;
    line-height: 129.164%;
    letter-spacing: 0.449vw;
    margin-bottom: 4vw;
}
#pta{
    margin: 0%;
    color: #483221;
    font-family: Kumbh Sans;
    font-size: 4.6vw;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.047vw;
    margin-bottom: 3vw;
}
}
/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
#homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 140vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    transform: translate(0%, 0vw);
    top: 30vw;
    left: 8vw;
}
#address{
    margin: 0%;
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.047vw;
    font-size: 3.27vw;
}
#siths{
    color: var(--text-color);
    color: #483221;
    text-align: left;
    font-family: Kumbh Sans;
    margin: 0%;
    font-size: 8vw;
    font-style: normal;
    font-weight: 800;
    line-height: 129.164%;
    letter-spacing: 0.449vw;
    margin-bottom: .2vw;
}
#pta{
    margin: 0%;
    color: #483221;
    font-family: Kumbh Sans;
    font-size: 4.1vw;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.047vw;
    margin-bottom: .4vw;
}
}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {
    #homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 70vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    transform: translate(0%, 0vw);
    top: 18vw;
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
}

@media only screen and (min-width: 1200px) {
    #homeTopCon{
    background: linear-gradient(180deg, #FFC498 0%, #FFD88C 28.65%, #FFD88C 61.98%, #FCE5AC 81.25%, #FFF 98.95%, #FFF 98.96%);
    width: 100vw;
    height: 70vw;
    margin: 0;
    padding: 0%;
    position: absolute;
    top: 0%;
    left: 0%;
}
#homeTopText{
    position: absolute;
    transform: translate(0%, 0vw);
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
}
</style>
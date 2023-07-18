<template>
    <div class="container__PTAInformation">
        <div class="container__SocialMedias">
            <a href=" " target="_blank" rel="noopener">
                <img src="/SocialMedias/facebook.svg" alt="facebook icon">
            </a>
            <a href=" " target="_blank" rel="noopener">
                <img src="/SocialMedias/instagram.svg" alt="instagram icon">
            </a>
            <a href=" " target="_blank" rel="noopener">
                <img src="/SocialMedias/twitter.svg" alt="twitter icon">
            </a>
        </div>
        <div class="container__TextInformation">
            <p>
                sitechpta@gmail.com
            </p>
            <p>485 Clawson Street, Staten Island, NY 10306</p>
        </div>
    </div>
</template>

<style scoped>
@import url(../assets/base.css);

.container__SocialMedias {
    display: flex;
    flex-direction: row;
    width: 15rem;
    justify-content: space-evenly;
    margin-bottom: 0.5rem;
}

.container__TextInformation {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.container__PTAInformation {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
p {
    font-family: var(--font-text);
    color: var(--text-color);
    text-align: center;
    font-size: 1.375rem;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    margin: 0.5rem;
}

@media only screen and (max-width: 480px) {
    p{
        font-size: 1rem;
    }
}
</style>

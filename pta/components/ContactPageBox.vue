<template>
  <div class="container__ContactPageBox">
    <h1>{{ props.header }}</h1>
    <div class="information">
      <p>{{ props.information }}</p>
    </div>
    <div id="extend">
      <p>:CCC</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  header: String,
  information: String,
});
</script>

<style scoped>
@import "../assets/base.css";
#extend {
  width: 100vw;
  height: 25vw;
  background-color: rgb(17, 105, 76);
  position: absolute;
  bottom: 0vw;
}
h1 {
  color: #483221;
  font-family: var(--font-heading);
  font-size: 2.5rem;
  font-style: normal;
  font-weight: 800;
  line-height: normal;
  letter-spacing: 0.05rem;
  margin: 0;
  text-decoration: #ffd88c underline;
  text-align: center;
}

.information {
  color: #483221;
  font-family: var(--font-text);
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: 129.164%;
  margin-top: 1.5rem;
  text-align: center;
}

.container__ContactPageBox {
  width: 77rem;
  height: 43.5rem;
  background-color: #fcf6e9;
  border-radius: 3.25rem;
  box-shadow: 2rem 2rem #ffd88c;
  display: flex;
  flex-direction: column;
  align-content: center;
  padding: 2rem 2rem 2rem 5rem;
}
</style>

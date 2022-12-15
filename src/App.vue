<template>
  <div>
    <DogWorldNavigation />
    <DogWorldHero id="hero" />
    <DogWorldLetsTalk id="lets-talk" heroForm="false" />
  </div>
</template>

<script>
import DogWorldNavigation from "./components/DogWorldNavigation.vue";
import DogWorldHero from "./components/DogWorldHero.vue";
import DogWorldLetsTalk from "./components/DogWorldLetsTalk.vue";

export default {
  name: "App",
  components: {
    DogWorldNavigation,
    DogWorldHero,
    DogWorldLetsTalk,
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  src: url("./assets/fonts/Rubik-Light.ttf") format("ttf");
}
@font-face {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  src: url("./assets/fonts/Rubik-Medium.ttf") format("ttf");
}
@font-face {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  src: url("./assets/fonts/Rubik-Regular.ttf") format("ttf");
}
@font-face {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  src: url("./assets/fonts/Rubik-Bold.ttf") format("ttf");
}
* {
  font-family: "Rubik", sans-serif;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}
#app {
  font-family: "Rubik", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.interior {
  max-width: 1440px;
  margin: auto;
}
</style>

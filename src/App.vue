<template>
  <div>
    <DogWorldNavigation />
  </div>
</template>

<script>
import DogWorldNavigation from "./components/DogWorldNavigation.vue";

export default {
  name: "App",
  components: {
    DogWorldNavigation,
  },
};
</script>

<style lang="scss">
$font: "Rubik";
@font-face {
  font-family: $font;
  font-style: normal;
  font-weight: 300;
  src: url("./assets/fonts/Rubik-Light.ttf") format("ttf");
}
@font-face {
  font-family: $font;
  font-style: normal;
  font-weight: 400;
  src: url("./assets/fonts/Rubik-Medium.ttf") format("ttf");
}
@font-face {
  font-family: $font;
  font-style: normal;
  font-weight: 500;
  src: url("./assets/fonts/Rubik-Regular.ttf") format("ttf");
}
@font-face {
  font-family: $font;
  font-style: normal;
  font-weight: 700;
  src: url("./assets/fonts/Rubik-Bold.ttf") format("ttf");
}
* {
  font: $font;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <game />
  </div>
</template>

<script>
import Game from "./components/Game";

export default {
  components: {
    Game,
  },
};
</script>

<style>
@font-face {
  font-family: "Star Jedi", arial;
  src: url("./fonts/star-jedi_[allfont.net].ttf");
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0px;
  background-image: url("./assets/background.jpg");
  background-attachment: fixed;
}
</style>

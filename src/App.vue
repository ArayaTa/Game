<template>
  <div id="app">
    <Game />
  </div>
</template>

<script>
import Game from "./assets/components/Game.vue";

export default {
  name: "App",
  components: {
    Game,
  },
};
</script>

<style>
#app {
  background-image: url(https://i.pinimg.com/originals/ff/1d/88/ff1d8824966668a2eb271133549d5d79.gif);
  height: 100%;
  background-size: cover; 
  background-repeat: no-repeat;
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: auto;
  padding: 0px;
}
</style>

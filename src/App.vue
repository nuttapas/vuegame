<template>
  <div id="app" class>
      <vuegame />
    <player />
  </div>
</template>

<script>

import vuegame from "./components/vuegame";

export default {
  name: "App",
  components: {
    
    vuegame,
  },
};
</script>

<style>
#app {
  font-family: 'Londrina Solid', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #646464;
}
</style>

<template>
  <div id="app">
    <vuegame/>
  <p>{{choseName}}</p>
</div>
</template>

<script>
import vuegame from './components/vuegame.vue'

export default {
  name: 'App',
  components: {
  vuegame,
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

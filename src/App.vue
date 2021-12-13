<template>
  <div id="app">
    <game></game>
    <score></score>
  </div>
</template>

<script>
import Game from './components/Game'
import Score from './components/Score'

export default {
  name: 'App',
  components: {
    Game,
    Score
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

<template>
  <div class="player">
    {{ welcomeMessage }}
  </div>
</template>

<script>
export default {
  name: 'player',
  created: function () {
    this.player = 'Ronaldo'
    this.welcomeMessage = this.player ? 'Bonjour ' + this.player + ' !' : 'Pas de joueur.'
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

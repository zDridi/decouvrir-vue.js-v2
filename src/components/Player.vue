<template>
  <div>
    <span v-hide>
      {{ welcomeMessage }}
    </span>
    <form v-hide>
      <input name="player" placeholder="Entrez votre nom de joueur" v-border:red/>
      <button type="submit" v-border:yellow>Jouer</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'player',
  created: function () {
    this.player = ''
    this.welcomeMessage = this.player ? 'Bonjour ' + this.player + ' !' : 'Pas de joueur'
  },
  directives: {
    border: function (el, binding) {
      el.style.borderColor = binding.arg
    },
    hide: function (el, binding, vnode) {
      let isForm = vnode.tag === 'form'
      console.log(isForm)
      let isSpan = vnode.tag === 'span'
      console.log(isSpan)
      let player = vnode.context.player
      console.log(player)

      if (isForm) {
        el.style.diplay = player ? 'none' : 'block'
      } else if (isSpan) {
        el.style.display = player ? 'block' : 'none'
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

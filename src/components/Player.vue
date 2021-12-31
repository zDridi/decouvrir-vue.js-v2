<template>
  <div>
    <span  v-html="welcomeMessage" v-hide>

    </span>
    <form v-hide v-on:submit.prevent="setPlayer">
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
    this.welcomeMessage = this.player ? `Bonjour <span class="player">${this.player}</span> !` : `Pas de joueur`
  },
  methods: {
    setPlayer: function (event) {
      console.log(event)
    }
  },
  directives: {
    border: function (el, binding) {
      el.style.borderColor = binding.arg
    },
    hide: function (el, binding, vnode) {
      let isForm = vnode.tag === 'form'
      console.log(vnode.tag)
      let player = vnode.context.player
      console.log(vnode.context.player)
      if (isForm) {
        el.style.display = player ? 'none' : 'block'
      } else {
        el.style.display = player ? 'block' : 'none'
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

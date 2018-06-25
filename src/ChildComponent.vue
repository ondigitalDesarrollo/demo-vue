<template lang="pug">
  main
    h1 Child LocalComponent.vue
    hr
    div
      h2  Contador
      p El valor es: {{ count }}
      p El doble es: {{ getDouble }}
      div
        button(@click="increment") +
        button(@click="decrement") -
      div
        button(@click="increment10") +10
</template>

<script>
import { mapState, mapMutations, mapGetters } from 'vuex'

export default {
  name: 'child',
  computed: {
    ...mapState(['count']),
    ...mapGetters(['getDouble'])
  },
  methods: {
    ...mapMutations(['increment', 'decrement']),
    increment10 () {
      this.$store.commit('increment', {
        number: 10
      })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

<template>
  <Header title='Dice Roller' /> <!-- title is essentially passing in parameters to the component -->
  <Tasks :rolls="rolls" /> <!-- Binds rolls prop to rolls data below -->
</template>

<script>
import Header from './components/Header'
import Rolls from './components/Rolls'

export default {
  name: 'App',
  components: {
    Header,
    Rolls
  },
  data() {
    return {
      rolls: []
    }
  },
  created() {
    this.rolls = [
      {
        id: 1,
        roll: "1d20",
        result: 20
      },
      {
        id: 2,
        roll: "3d6+5",
        result: 16
      },
      {
        id: 3,
        roll: "1d20+7",
        result: 15
      }
    ]
  }
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

<template>
  <Header title='Dice Roller' /> <!-- title is essentially passing in parameters to the component -->
  <Rolls @delete-roll="deleteRoll" :rolls="rolls" /> <!-- Dynamically binds rolls data -->
</template>

<script>
import Header from "./components/Header"
import Rolls from "./components/Rolls.vue"

export default {
  name: "App",
  components: {
    Header,
    Rolls
  },
  data() {
    return {
      rolls: []
    }
  },
  methods: {
    deleteRoll(id) {
      if (confirm("Are you sure?")) {
        this.rolls = this.rolls.filter((roll) => roll.id !== id)
      }
    }
  },
  created() {
    this.rolls = [
      {
        id: 1,
        roll: "1d20+5",
        result: "25",
        crit_fail: false,
        crit_succ: true
      },
      {
        id: 2,
        roll: "1d20+5",
        result: "1",
        crit_fail: true,
        crit_succ: false
      },
      {
        id: 3,
        roll: "1d12",
        result: "11",
        crit_fail: false,
        crit_succ: false
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

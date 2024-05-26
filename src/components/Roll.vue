<template>
<div
  class="roll">
  <h3>{{ roll.roll }}: <i @click="onDelete(roll.id)" class="fas fa-times"></i></h3>
  <p :class="{ fail: roll.crit_fail, succ: roll.crit_succ }">{{ roll.result }}</p>
  <span id="delete" @click="removeRoll(roll.id)">X</span>
</div>
</template>

<script>
export default {
  name: "Roll",
  props: {
    roll: Object
  },
  methods: {
    removeRoll(id) {
      this.$emit("remove-roll", id) /* Data is at highest level (App --> Rolls --> Roll) so we need to emit the vent upwards. lowercase-dash is the convention */
    }
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-roll", id) // using dash is the convention
    }
  }
}
</script>

<style scoped>

.roll {
  background-color: lightgray;
  width: 30%;
  margin: 0 auto;
  position: relative;
}

.fail {
  color: red;
}

.succ {
  color: green;
}

#delete {
  position: absolute;
  margin-top: 3px;
  margin-right: 3px;
  top: 0;
  right: 0;
  color: red;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  cursor: pointer;
}

.roll {
  padding: 0px;
}

.fas {
  color: red;
  margin-right: 3px;
}

.roll h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

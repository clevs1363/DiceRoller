<template>
<div
  class="roll">
  <h3>{{ roll.roll }}: <i @click="onDelete(roll.id)" class="fas fa-times"></i></h3>
  <p :class="{ fail: roll.crit_fail, succ: roll.crit_succ }">{{ roll.result }}</p>
</div>
</template>

<script>
export default {
  name: "Roll",
  props: {
    roll: Object
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-roll", id) // using dash is the convention
    }
  }
}
</script>

<style scoped>

div {
  background-color: lightgray;
  width: 30%;
  margin: 0 auto;
}

.fail {
  color: red;
}

.succ {
  color: green;
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

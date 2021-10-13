<template>
<div
  class="roll">
  <h3>{{ roll.roll }}: </h3>
  <p :class="{ fail: roll.crit_fail, succ: roll.crit_succ }">{{ roll.result }}</p>
</div>
</template>

<script>
export default {
  name: "Roll",
  props: {
    roll: Object
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

</style>

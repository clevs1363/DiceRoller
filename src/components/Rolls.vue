<template>
  <div :key="roll.id" v-for="roll in rolls">
    <Roll @delete-roll="$emit('delete-roll', roll.id)" :roll="roll" />
  </div>

  <Button />
</template>

<script>
import Roll from "./Roll"
import Button from "./Button"

export default {
  name: "Rolls",
  props: {
    rolls: Array
  },
  components: {
    Roll,
    Button
  },
  emits: ["delete-roll"]
}
</script>

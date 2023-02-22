<template>
  <div :key="roll.id" v-for="roll in rolls">
    <Roll @remove-roll="$emit('remove-roll', roll.id)" :roll="roll" />
  </div>
  <form>
    <input type="text" id="roller" name="roller" placeholder="Roll"><br><br>
    <input type="submit" value="Submit">
  </form>
</template>

<script>
import Roll from "./Roll"

export default {
  name: "Rolls",
  props: {
    rolls: Array
  },
  components: {
    Roll
  },
  emits: ["remove-roll"]
}
</script>

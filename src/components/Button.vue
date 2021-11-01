<template>
  <form>
    <input type="text" id="roller" name="roller" placeholder="Roll"><br><br>
    <input @click='onClick()' type="submit" value="Add roll"> <!-- @click triggers an event, equivalent to v-on:click= -->
  </form>
</template>

<script>
export default {
  name: "Button",
  methods: {
    onClick() {
      console.log("click")
    }
  }
}
</script>

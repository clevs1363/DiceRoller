<template>
<header>
  <h1>{{ title }}</h1>
</header>
</template>

<script>
import Button from "./Button"

export default {
  name: "Header",
  props: {
    title: {
      type: String,
      default: "<title not found>"
    }
  },
  /* Can also use a simple array - props: ['title'] */
  components: {
    // Button
  }
}
</script>

<style scoped> /* scoped means only this component receives this styling */
header {
  color: green;
}
</style>

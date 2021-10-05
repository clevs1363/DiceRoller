<template>
  <button @click='onClick()' class='btn'>Add roll</button> <!-- @click triggers an event, equivalent to v-on:click= -->
</template>

<script>
export default {
  name: 'Button',
  methods: {
    onClick() {
      console.log('click')
    }
  }
}
</script>

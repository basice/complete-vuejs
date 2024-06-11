<template>
  <my-button
    color="white"
    background="darkslateblue"
    v-bind:disabled="!valid"
  />
</template>

<script>
import MyButton from './MyButton.vue'

export default {
  components: { MyButton },
  data() {
    return {
      valid: false
    }
  }
}
</script>

<style scoped></style>

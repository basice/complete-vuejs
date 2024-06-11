<template>
  <my-input
    name="Username"
    :rules="{ required: true, min: 5 }"
  ></my-input>

  <my-input
    name="Password"
    :rules="{ required: true, min: 10 }"
  ></my-input>

  <my-button
    color="white"
    background="darkslateblue"
    :disabled="!valid"
  />
</template>

<script>
import MyButton from './MyButton.vue'
import MyInput from './MyInput.vue'

export default {
  components: {
    MyButton,
    MyInput
  },
  data() {
    return {
      valid: true
    }
  }
}
</script>

<style scoped></style>

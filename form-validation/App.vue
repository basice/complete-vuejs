<template>
  {{ username }}
  <my-input
    name="Username"
    :rules="{ required: true, min: 5 }"
    :value="username.value"
    @update="update"
  ></my-input>

  {{ password }}
  <my-input
    name="Password"
    :rules="{ required: true, min: 10 }"
    :value="password.value"
    @update="update"
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
      valid: true,
      username: {
        value: '',
        valid: false
      },
      password: {
        value: '',
        valid: false
      }
    }
  },
  methods: {
    update(payload) {
      // square bracket for dynamic key
      this[payload.name.toLowerCase()].value = payload.value
    }

  }
}
</script>

<style scoped></style>

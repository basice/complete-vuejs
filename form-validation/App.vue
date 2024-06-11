<template>
  {{ username }}
  <my-input
    name="Username"
    :rules="{ required: true, min: 5 }"
    :value="username.value"
    @update="update"
    type="text"
  ></my-input>

  {{ password }}
  <my-input
    name="Password"
    :rules="{ required: true, min: 10 }"
    :value="password.value"
    @update="update"
    type="password"
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
  computed: {
    valid() {
      return this.username.valid && this.password.valid
    }
  },
  methods: {
    update(payload) {
      // square bracket for dynamic key
      this[payload.name.toLowerCase()] = {
        value: payload.value,
        valid: payload.valid
      }
    }
  }
}
</script>

<style scoped></style>

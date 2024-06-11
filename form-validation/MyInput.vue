<template>
  <div class="input-wrapper">
    <div class="label">
      <label :for="name">{{ name }}</label>
      <div class="error">{{ error }}</div>
    </div>

    <input
      :id="name"
      type="text"
      v-model="value"
    >
  </div>

</template>


<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    rules: {
      type: Object // min, required
    }
  },
  data() {
    return {
      value: ''
    }
  },
  computed: {
    error() {
      if (this.rules.required && !this.value) {
        return 'Required'
      }
      if (this.rules.min && this.value.length < this.rules.min) {
        return `Minimum length is ${this.rules.min}`
      }
    }
  }
}
</script>


<style scoped>
.input-wrapper {
  display: flex;
  flex-direction: column;
}

.error {
  color: red;
}

.label {
  display: flex;
  justify-content: space-between;
}

input {
  padding: 10px;
  border-radius: 8px;
  border: 1px solid silver;
  margin: 2px;
  font-size: 16px;
  cursor: pointer;
}
</style>
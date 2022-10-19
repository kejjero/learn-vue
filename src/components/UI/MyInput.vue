<template>
  <input type="text" placeholder="Заголовок" class="input" @input="updateInput" :value="value">
</template>

<script>
export default {
  name: "my-input",
  props: {
    value: [String, Number]
  },
  methods: {
    updateInput(evt) {
      this.$emit("update:value", evt.target.value)
    }
  }
}
</script>

<style scoped>
.input {
  margin: 0;
  padding: 10px 5px;
  width: 100%;
}
</style>
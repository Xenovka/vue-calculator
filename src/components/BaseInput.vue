<template>
  <input
    @input="inputValidation"
    type="text"
    id="the-input"
    class="calc-input bg-darker"
  />
</template>

<script>
export default {
  methods: {
    inputValidation(event) {
      let inputValue = event.target.value;
      const inputElement = document.getElementById("the-input");

      const nonNumber = /([^a-zA-Z\D]){1,}/g;
      const invalidInput = inputValue.match(nonNumber);
      inputElement.value = invalidInput.join("");
    }
  }
};
</script>

<style scoped>
@import "../assets/css/Input.css";
</style>

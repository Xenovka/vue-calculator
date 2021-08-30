<template>
  <button
    @click="getValueFromButton"
    class="btn"
    :class="btnClass"
    :value="value"
  >
    {{ buttonValue }}
  </button>
</template>

<script>
export default {
  props: ["value"],
  data() {
    return {
      btnItem: this.value
    };
  },
  methods: {
    getValueFromButton(event) {
      const inputElement = document.querySelector("input");
      const buttonValue = event.target.value;

      inputElement.value += !isNaN(buttonValue) ? buttonValue : "";

      if (buttonValue === "reset") {
        inputElement.value = "";
      } else if (buttonValue === "delete") {
        inputElement.value = inputElement.value.slice(
          0,
          inputElement.value.length - 1
        );
      }
    }
  },
  computed: {
    btnClass() {
      if (
        this.value !== "equal" &&
        this.value !== "delete" &&
        this.value !== "reset"
      ) {
        return `btn-${this.btnItem} btn-light`;
      } else if (this.value === "equal") {
        return `btn-${this.btnItem} btn-red`;
      } else {
        return `btn-${this.btnItem} btn-dark`;
      }
    },
    buttonValue() {
      if (typeof this.value === "number") {
        return this.value;
      }

      switch (this.value) {
        case "equal":
          return "=";
        case "mod":
          return "%";
        case "plus":
          return "+";
        case "minus":
          return "-";
        case "times":
          return "×";
        case "divided":
          return "÷";
        case "delete":
          return "DEL";
        case "reset":
          return "RESET";
        default:
          return null;
      }
    }
  }
};
</script>

<style scoped>
@import "../assets/css/Button.css";
</style>

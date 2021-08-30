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

      inputElement.value += !isNaN(event.target.value)
        ? event.target.value
        : "";

      if (event.target.value === "reset") {
        inputElement.value = "";
      } else if (event.target.value === "delete") {
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
        case "comma":
          return ".";
        case "plus":
          return "+";
        case "minus":
          return "-";
        case "times":
          return "x";
        case "divided":
          return "/";
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

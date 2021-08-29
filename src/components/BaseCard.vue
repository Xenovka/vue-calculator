<template>
  <div class="card-container grid-container bg-dark">
    <the-button v-for="n in 10" :key="n" :value="n - 1"></the-button>
    <the-button
      v-for="operator in operators"
      :key="operator"
      :value="operator"
    ></the-button>
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";

export default {
  data() {
    return {
      operators: [
        "equal",
        "comma",
        "plus",
        "minus",
        "times",
        "divided",
        "delete",
        "reset"
      ]
    };
  },
  components: {
    TheButton
  }
};
</script>

<style scoped>
@import "../assets/css/Card.css";
</style>

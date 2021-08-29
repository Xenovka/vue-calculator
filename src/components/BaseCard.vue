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
.card-container {
  width: 45rem;
  height: 40rem;
  border-radius: 10px;
  position: absolute;
  top: 65%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 2rem;
}

.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-template-rows: auto auto auto auto auto;
  grid-column-gap: 1rem;
  justify-content: space-evenly;
}
</style>

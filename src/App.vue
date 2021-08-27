<template>
  <base-input></base-input>
  <base-card></base-card>
</template>

<script>
import BaseCard from "./components/BaseCard.vue";
import BaseInput from "./components/BaseInput.vue";

export default {
  components: {
    BaseCard,
    BaseInput
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Spartan:wght@400;500;700;800&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-size: 62.5%;
  font-family: "Spartan", sans-serif;
}

body {
  background-color: hsl(222, 26%, 31%);
}

.bg-dark {
  background-color: hsl(223, 31%, 20%);
}

.bg-darker {
  background-color: hsl(224, 36%, 15%);
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type="number"] {
  -moz-appearance: textfield;
}

input:focus {
  text-decoration: none;
}
</style>

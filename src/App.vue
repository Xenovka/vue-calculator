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
@import "./assets/css/GlobalStyling.css";
</style>

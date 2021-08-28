<template>
  <div class="card-container grid-container bg-dark">
    <the-button v-for="n in 9" :key="n" :value="n"></the-button>
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";

export default {
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
  grid-template-columns: 10rem 10rem 10rem 10rem;
  grid-template-rows: 7rem 7rem 7rem 7rem 7rem;
  grid-column-gap: 1rem;
}
</style>

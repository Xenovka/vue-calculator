<template>
  <button class="btn btn-number">{{ value }}</button>
</template>

<script>
export default {
  props: ["value"]
};
</script>

<style scoped>
.btn {
  width: 10rem;
  font-size: 2rem;
  font-weight: 700;
  padding: 2rem;
  margin: 1rem 0 0 1rem;
}
</style>

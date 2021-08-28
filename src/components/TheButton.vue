<template>
  <button class="btn btn-light" :class="btnClass">{{ value }}</button>
</template>

<script>
export default {
  props: ["value"],
  data() {
    return {
      btnItem: this.value
    };
  },
  computed: {
    btnClass() {
      return "btn-" + this.btnItem;
    }
  }
};
</script>

<style scoped>
.btn {
  width: 8.5rem;
  height: 5rem;
  font-size: 3rem;
  font-weight: 700;
  padding: 1rem;
  cursor: pointer;
  border: none;
  border-radius: 10px;
}

.btn-light {
  background-color: hsl(30, 25%, 89%);
  box-shadow: 0 0.3rem hsl(28, 16%, 65%);
}

.btn-dark {
  background-color: hsl(225, 21%, 49%);
  box-shadow: 0 0.3rem hsl(224, 28%, 35%);
}

.btn-red {
  background-color: hsl(6, 63%, 50%);
  box-shadow: 0 0.3rem hsl(6, 70%, 34%);
}

.btn-1,
.btn-2,
.btn-3 {
  grid-row-start: 3;
  grid-row-end: 4;
}

.btn-4,
.btn-5,
.btn-6 {
  grid-row-start: 2;
  grid-row-end: 3;
}

.btn-7,
.btn-8,
.btn-9 {
  grid-row-start: 1;
  grid-row-end: 2;
}
</style>

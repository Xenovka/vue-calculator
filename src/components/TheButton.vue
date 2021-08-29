<template>
  <button class="btn" :class="btnClass">{{ buttonValue }}</button>
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

.btn-equal,
.btn-reset,
.btn-delete {
  font-size: 1.5rem;
  color: white;
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
.btn-9,
.btn-delete {
  grid-row-start: 1;
  grid-row-end: 2;
}

.btn-0,
.btn-comma,
.btn-divided {
  grid-row-start: 4;
  grid-row-end: 5;
}

.btn-reset,
.btn-equal {
  grid-row-start: 5;
  grid-row-end: 6;
}

.btn-0 {
  grid-column-start: 2;
  grid-column-end: 3;
}

.btn-delete,
.btn-plus,
.btn-minus,
.btn-times {
  grid-column-start: 4;
  grid-column-end: 5;
}

.btn-reset {
  grid-column: 1 / span 2;
}

.btn-equal {
  grid-column: 3 / span 2;
}

.btn-reset,
.btn-equal {
  width: 100%;
}
</style>

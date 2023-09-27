<template>
  <div>{{ fullName }}</div>
  <div>{{ userName }}</div>
  <button ref="btn">Click!</button>
</template>

<script>
export default {
  props: {
    name: String,
    lastName: String,
  },
  inject: ["userName"],
  computed: {
    fullName() {
      return `${this.name} ${this.lastName}`;
    },
  },
  mounted() {
    console.log(this.$refs.btn);
  },
};
</script>

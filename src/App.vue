<template>
  <div>
    <p>{{ message }}</p>
    <button @click="changeMessage">change</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "hello",
    };
  },
  methods: {
    changeMessage() {
      this.message = "hi";
    },
  },
};
</script>

<style lang="scss" scoped></style>

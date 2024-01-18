<template>
  <todo-header></todo-header>
  <todo-input></todo-input>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
export default {
  components: {
    TodoHeader,
    TodoInput,
  },
};
</script>

<style lang="scss" scoped></style>

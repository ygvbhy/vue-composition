<template>
  <todo-header></todo-header>
  <todo-input></todo-input>
  <todo-list :todoItems="todoItems"></todo-list>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import { ref } from "vue";
export default {
  components: {
    TodoHeader,
    TodoInput,
    TodoList,
  },
  setup() {
    const todoItems = ref([]);

    function fetchTodos() {
      const result = [];
      for (let i = 0; i < localStorage.length; i++) {
        const todoItem = localStorage.key(i);
        // items.value.push(todoItem);
        result.push(todoItem);
      }
      return result;
    }

    todoItems.value = fetchTodos();

    return { todoItems };
  },
};
</script>

<style lang="scss" scoped></style>

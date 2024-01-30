<template>
  <todo-header></todo-header>
  <todo-input @add="addTodo"></todo-input>
  <todo-list :todoItems="todoItems" @delete="deleteTodoItem"></todo-list>
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

    function addTodo(todo) {
      todoItems.value.push(todo);
      localStorage.setItem(todo, todo);
    }

    return { todoItems, addTodo };
  },
  methods: {
    deleteTodoItem(item, index) {
      this.todoItems.splice(index, 1);
      localStorage.removeItem(item);
    },
  },
};
</script>

<style lang="scss" scoped></style>

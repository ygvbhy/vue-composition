<template>
  <ul>
    <li v-for="(item, index) in todoItems" :key="index">
      <span>{{ item }}</span>
      <button @click="deleteTodo(item, index)">삭제</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    todoItems: {
      type: Array,
    },
  },
  setup(props, context) {
    function deleteTodo(item, index) {
      context.emit("delete", item, index);
    }

    return { deleteTodo };
  },
};
</script>

<style lang="scss" scoped></style>

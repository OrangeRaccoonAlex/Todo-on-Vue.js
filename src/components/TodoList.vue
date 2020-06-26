<template>
  <ul class="todo-list-list">
    <TodoListItem v-for="item in items" :key="item.id" :item="item" />
  </ul>
</template>

<script>
import TodoListItem from "@/components/TodoListItem.vue";
export default {
  name: "TodoList",
  components: { TodoListItem },
  props: {
    items: {
      type: Array,
      default: () => []
    }
  }
};
</script>
<style>
.todo-list-list {
  width: 500px;
  margin: 0 auto;
  list-style: none;
  padding: 0;
  text-align: left;
}
</style>

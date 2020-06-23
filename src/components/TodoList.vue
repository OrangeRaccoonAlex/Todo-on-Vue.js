<template>
  <ul>
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

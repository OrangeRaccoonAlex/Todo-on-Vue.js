<template>
  <li class="todo-list-todo">
    <input type="checkbox" v-model="isComplete" />
    <div>{{ text }}</div>
  </li>
</template>

<script>
export default {
  name: "TodosListItem",
  props: {
    item: {
      required: true,
      type: Object
    }
  },
  data() {
    return {
      id: null,
      text: "",
      isComplete: false
    };
  },
  created() {
    this.id = this.item.id;
    this.text = this.item.text;
    this.isComplete = this.item.isComplete;
  }
};
</script>

<style>
.todo-list-todo {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
  border-bottom: solid 1px #ddd;
}
.todo-list-todo div {
  font-size: 1.3rem;
}
.todo-list-todo input {
  margin-right: 10px;
  width: 20px;
  height: 20px;
}
</style>

<template>
  <li class="todo-list-todo">
    <input type="checkbox" :value="isComplete" @input="newTodos(isComplete)" />
    <div>{{ text }}</div>
    <button @click="removeTodo(id)">×</button>
  </li>
</template>

<script>
export default {
  name: "TodosListItem",
  props: {
    id: {
      type: Number,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    isComplete: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    removeTodo(index) {
      this.$emit("remove-todo-item", index);
    },
    newTodos(isComplete) {
      this.$emit("new-todos", this.id, isComplete);
    }
  }
};
</script>

<style>
.todo-list-todo {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
  border-bottom: solid 1px #ddd;
  padding-bottom: 5px;
}
.todo-list-todo div {
  font-size: 1.3rem;
  flex-grow: 1;
}
.todo-list-todo input {
  margin-right: 10px;
  width: 20px;
  height: 20px;
}
.todo-list-todo button {
  border-radius: 50%;
  color: rgb(187, 61, 61);
  widows: 24px;
  height: 30px;
  border: solid 1px #ddd;
  cursor: pointer;
  font-size: 1.4rem;
  opacity: 0;
  box-sizing: border-box;
  z-index: -1;
  transition: all 0.3s ease;
}
.todo-list-todo:hover button {
  opacity: 1;
  z-index: 1;
}
</style>

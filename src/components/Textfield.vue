<template>
  <div>
    <input v-model="message" @keyup.enter="addTodo" class="todo-input" />
  </div>
</template>

<script>
export default {
  name: "Textfield",
  props: {
    sendText: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      message: ""
    };
  },
  methods: {
    addTodo() {
      this.$emit("add-todo-item", this.message);
    }
  }
};
</script>
<style>
.todo-input {
  box-sizing: border-box;
  width: 500px;
  padding: 20px 30px;
  border: solid 1px #ddd;
  font-size: 1.5rem;
  color: #555;
  outline: none;
  border-radius: 3px;
  transition: all 0.3s ease;
  box-shadow: 1px 5px 5px rgb(227, 227, 227);
  margin: 10px 0 50px;
}
.todo-input:focus {
  border: solid 1px #bbb;
}
.todo-input:active {
  border: solid 1px #bbb;
}
</style>

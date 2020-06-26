<template>
  <div class="home">
    <Header app-name="My first Todo with Vue" />
    <Textfield @add-todo-item="showTodo" />
    <TodoList :items="todos" />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Textfield from "@/components/Textfield.vue";
import TodoList from "@/components/TodoList.vue";

export default {
  name: "Home",
  components: {
    Header,
    Textfield,
    TodoList
  },
  data() {
    return {
      todos: [
        { id: 0, text: "Выучить JavaScript", isComplete: true },
        { id: 1, text: "Выучить Vue", isComplete: true },
        { id: 2, text: "Погулять", isComplete: false },
        { id: 3, text: "Поиграть в шахматы", isComplete: false },
        { id: 4, text: "Приготовить вкусный ужин", isComplete: true },
        { id: 5, text: "Поиграть в Скайрим", isComplete: false }
      ]
    };
  },
  methods: {
    showTodo(content) {
      this.todos.push(this.createTodo(content));
    },
    createTodo(title) {
      let max = 0;
      for (let i = 0; i < this.todos.length; i++) {
        if (this.todos[i].id > max) {
          max = this.todos[i].id + 1;
        }
      }
      return {
        isComplete: false,
        text: title,
        id: max
      };
    }
  }
};
</script>

<template>
  <div class="home">
    <Header app-name="My first Todo with Vue" />
    <Textfield @add-todo-item="showTodo" />
    <TodoList
      :items="filtration"
      @remove-todo-on-main="deleteTodo"
      @update-new-todos="changeTodos"
    />
    <ButtonGroup @set-filter="setFilterButton" :currentFilter="filterButton" />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Textfield from "@/components/Textfield.vue";
import TodoList from "@/components/TodoList.vue";
import ButtonGroup from "@/components/ButtonGroup.vue";

export default {
  name: "Home",
  components: {
    Header,
    Textfield,
    TodoList,
    ButtonGroup
  },
  data() {
    return {
      index: null,
      todos: [],
      filterButton: "all"
    };
  },
  created() {
    this.getData();
  },
  computed: {
    filtration() {
      switch (this.filterButton) {
        case "active":
          return this.todos.filter(todo => todo.isComplete === false);
        case "completed":
          return this.todos.filter(todo => todo.isComplete !== false);
        case "all":
        default:
          return this.todos;
      }
    }
  },
  methods: {
    getData() {
      function getResponse(response) {
        return response.json();
      }
      let setTodos = todos => {
        this.todos = todos;
      };
      fetch("http://localhost:3000/todos")
        .then(getResponse)
        .then(setTodos);
    },
    showTodo(content) {
      this.todos.push(this.createTodo(content));
    },
    deleteTodo(index) {
      this.todos = this.todos.filter(function(todo) {
        return todo.id !== index;
      });
    },
    createTodo(title) {
      let max = 0;
      for (let i = 0; i < this.todos.length; i++) {
        if (this.todos[i].id > max) {
          max = this.todos[i].id;
        }
      }
      return {
        isComplete: false,
        text: title,
        id: max + 1
      };
    },
    setFilterButton(filter) {
      this.filterButton = filter;
    },
    changeTodos(id, isComplete) {
      const itemTodos = this.todos.findIndex(todo => todo.id === id);
      const startTodos = this.todos.slice(0, itemTodos);
      const endTodos = this.todos.slice(itemTodos + 1);
      const newTodos = {
        id: id,
        text: this.todos[itemTodos].text,
        isComplete: isComplete
      };
      this.todos = [...startTodos, newTodos, ...endTodos];
    }
  }
};
</script>

<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Header app-name="My first Todo with Vue" />
    <Textfield />
    <TodoList :items="items" />
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
      items: [
        { id: 0, text: "Выучить JavaScript", isComplete: true },
        { id: 1, text: "Выучить Vue", isComplete: true },
        { id: 2, text: "Погулять", isComplete: false },
        { id: 3, text: "Поиграть в шахматы", isComplete: false },
        { id: 4, text: "Приготовить вкусный ужин", isComplete: true },
        { id: 5, text: "Поиграть в Скайрим", isComplete: false }
      ]
    };
  }
};
</script>

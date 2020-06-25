<template>
  <div>
    <input v-model="message" @keyup.enter="addTodo" />
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

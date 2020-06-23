<template>
  <li>
    <input type="checkbox" v-model="isComplete" />
    <span>{{ text }}</span>
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

<style></style>

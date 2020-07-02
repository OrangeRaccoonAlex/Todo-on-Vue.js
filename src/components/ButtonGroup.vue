<template>
  <div>
    <button
      class="default-button"
      :class="{'second-default-button': currentFilter === 'all'}"
      @click="show('all')"
    >Все</button>
    <button
      class="default-button"
      :class="{'second-default-button': currentFilter === 'active'}"
      @click="show('active')"
    >Активные</button>
    <button
      class="default-button"
      :class="{'second-default-button': currentFilter === 'completed'}"
      @click="show('completed')"
    >Завершенные</button>
  </div>
</template>

<script>
export default {
  name: "ButtonGroup",
  props: {
    currentFilter: {
      type: String,
      required: true
    }
  },
  methods: {
    show(filterSelected) {
      this.$emit("set-filter", filterSelected);
    }
  }
};
</script>

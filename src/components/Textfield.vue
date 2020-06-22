<template>
  <input v-model="message" />
</template>

<script>
export default {
  name: "Textfield",
  data() {
    return {
      message: ""
    };
  }
};
</script>

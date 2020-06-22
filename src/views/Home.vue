<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Header app-name="My first Todo with Vue" />
    <Textfield />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Textfield from "@/components/Textfield.vue";

export default {
  name: "Home",
  components: {
    Header,
    Textfield
  }
};
</script>

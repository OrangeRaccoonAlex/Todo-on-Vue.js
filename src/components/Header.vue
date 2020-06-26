<template>
  <div class="header">
    <h1>{{ appName }}</h1>
    <img alt="Vue logo" src="../assets/logo.png" />
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    appName: {
      type: String,
      required: true
    }
  }
};
</script>

<style>
.header {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  width: 1200px;
  text-align: center;
}
.header img {
  width: 50px;
  height: 50px;
}
</style>

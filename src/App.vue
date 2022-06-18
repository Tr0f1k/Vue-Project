<template>
  <InputTables />
</template>

<script>
import InputTables from './components/InputTables.vue';
export default {
  name: "App",
  components: {
    InputTables
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

html, body {
  background-color: #bee0c5;
}
</style>

<template>
<h1>Glass Calculations</h1>
<form action="#">
  <select name="23" id="someinput" @change="chooseCalculator()">
    <option value="default"></option>
    <option value="bending">Glass Bending</option>
    <option value="cutting">Glass Cutting</option>
  </select>
</form>
  <h1 id="somestuff">Choose one of the calculators from the list above</h1>
  <InputTables v-if="opt == 'bending'" />
  <First v-if="opt == 'cutting'" />
</template>

<script>
import InputTables from './components/Glass Bending/InputTables.vue';
import First from './components/glass cutting/First.vue';
import { nextTick } from 'vue';
export default {
  name: "App",
  components: {
    InputTables,
    First
  },
  data() {
    return {
      opt: ""
    }
  },
  methods: {
    async chooseCalculator() {
      this.opt = document.getElementById('someinput').value;
      await nextTick();
      console.log (this.opt);
      document.getElementById('somestuff').style.display="none";
      if (this.opt == 'default') {
        document.getElementById('somestuff').style.display="inline-block";
      }
    }
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

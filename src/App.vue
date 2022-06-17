<template>
   <header style="background: #bee0c5; text-align: center; font-size: 20px">Glass Bending Calculator!</header>
        <h1 style="padding-top: 0.01%"></h1>
        <table align="center" width="50%" style="background: #bee0c5; table-layout: fixed; text-align: center">
            <tr>
                <td>
                    Order ID: <input id="orderID">
                </td>
            </tr>
        </table>
        <h1 style="padding-top: 1%"></h1>
        <table width="30%" align="center" style="background: #bee0c5; table-layout: fixed; text-align: center;">
            <tr>
                <td>
                    <form action="#">
                        <label for="lang">Choose a way to calculate:</label>
                        <select name="choose" id="userinput" @change="openTable()">
                            <option value="default"></option>
                            <option value="sAndRise">Span and Rise</option>
                            <option value="sAndRad">Span and Radius</option>
                            <option value="radAndRise">Radius and Rise</option>
                            <option value="radAndG">Radius and Girth</option>
                            <option value="radAndA">Radius and Angle</option>
                        </select>
                    </form>
                </td>
            </tr>
        </table>
        <img src="@/assets/1.jpg" style="display: block; margin-left: auto; margin-right: auto; padding-top: 3%; width: 30%;">
  <InputTables :id="id"/>
</template>

<script>
import { nextTick } from 'vue';
import InputTables from './components/InputTables.vue'
export default {
  name: 'App',
  components: {
    InputTables,
  },
  data() {
    return {
      id: ''
    }
  },
  methods: {
    openTable () {
      this.id = document.getElementById('userinput').value;
      nextTick()
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

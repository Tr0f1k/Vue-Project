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
                        <select name="choose" id="userinput" v-on:change = "keyboardInput()">
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
</template>

<script>
import InputTables from "@/components/InputTables"
export default {
  name: 'HelloWorld',
    methods: {
      keyboardInput () {
        this.i = document.getElementById("userinput").value;
        this.$emit("openTables", this.i)
      }
    },
    components: {
    InputTables
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

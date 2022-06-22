<template>
   <h1 class="header">Glass Bending Calculator!</h1>
        <h1 class="firstPad"></h1>
        <table class="firstTable">
            <tr>
                <td>
                    Order ID: <input id="orderID">
                </td>
            </tr>
        </table>
        <h1 class="secondPad"></h1>
        <table class="secondTable">
            <tr>
                <td>
                        <label>Choose a way to calculate:</label>
                        <select id="userinput" @change="openTable()">
                            <option value="default"></option>
                            <option value="sAndRise">Span and Rise</option>
                            <option value="sAndRad">Span and Radius</option>
                            <option value="radAndRise">Radius and Rise</option>
                            <option value="radAndG">Radius and Girth</option>
                            <option value="radAndA">Radius and Angle</option>
                        </select>
                </td>
            </tr>
        </table>
        <img src="@/assets/1.jpg">
<SAndRise v-if="id == 'sAndRise'" />
<SAndRad v-if="id == 'sAndRad'" />
<RadAndRise v-if="id == 'radAndRise'" />
<RadAndG v-if="id == 'radAndG'" />
<RadAndA v-if="id == 'radAndA'" />
</template>

<script>
import SAndRise from './resultTables/SAndRise.vue';
import SAndRad from './resultTables/SAndRad.vue';
import RadAndRise from './resultTables/RadAndRise.vue';
import RadAndG from './resultTables/RadAndG.vue';
import RadAndA from './resultTables/RadAndA.vue';
import { nextTick } from 'vue';
export default {
    name:'InputTables',
    components: {
        SAndRise,
        SAndRad,
        RadAndRise,
        RadAndG,
        RadAndA
    },
    data() {
        return {
            id: '123'
        }
    },
    methods: {
    async openTable () {
      this.id = document.getElementById('userinput').value;
      await nextTick()
    }
    }
}
</script>

<style scoped>

.header {
    background: #bee0c5;
    text-align: center;
    font-size: 20px
}
.firstPad {
    padding-top: 0.01%
}

.secondPad {
    padding-top: 1%
}
.firstTable {
    background: #bee0c5;
    table-layout: fixed;
    text-align: center;
    align-items: center;
    width: 100%
}

.secondTable {
    background: #bee0c5;
    table-layout: fixed;
    text-align: center;
    width: 100%
}

img {
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top: 3%;
    width: 30%
}

</style>
<template>
   <h1 style="background: #bee0c5; text-align: center; font-size: 20px;">Glass Bending Calculator!</h1>
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
<Default v-if="id == 'default'" />
<SAndRise v-if="id == 'sAndRise'" />
<SAndRad v-if="id == 'sAndRad'" />
<RadAndRise v-if="id == 'radAndRise'" />
<RadAndG v-if="id == 'radAndG'" />
<RadAndA v-if="id == 'radAndA'" />
</template>

<script>
import Default from './result tables/Default.vue';
import SAndRise from './result tables/SAndRise.vue';
import SAndRad from './result tables/SAndRad.vue';
import RadAndRise from './result tables/RadAndRise.vue';
import RadAndG from './result tables/RadAndG.vue';
import RadAndA from './result tables/RadAndA.vue';
import { nextTick } from 'vue';
export default {
    name:'InputTables',
    components: {
        Default,
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
</style>
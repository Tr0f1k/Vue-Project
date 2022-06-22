<template>
<table>
            <tr>
                <td>
                    Height:
                </td>
                <td>
                    <input id="height4" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Thickness:
                </td>
                <td>
                    <input id="thickness4" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Radius:
                </td>
                <td>
                    <input id="7" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Girth:
                </td>
                <td>
                    <input id="8" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    <button id="button4" @click="radiusgirth()">Calculate!</button>
                </td>
            </tr>
        </table>
            <ResultTables
            v-if="but == false"
            :firstName="firstName"
            :firstValue="a"
            :firstMeasure="firstMeasure"
            :secondName="secondName"
            :secondValue="s"
            :secondMeasure="secondMeasure"
            :thirdName="thirdName"
            :thirdValue="rise"
            :thirdMeasure="thirdMeasure"
            :areaValue="ar"
            :weightValue="m"
            />
            <AngleWarning 
            v-if="a > 90"
            />
</template>

<script>
import ResultTables from './ResultTables.vue';
import AngleWarning from './AngleWarning.vue';
export default {
    name: "RadAndA",
    components: {
        ResultTables,
        AngleWarning
    },
    data() {
        return {
            firstName: 'Angle:',
            firstMeasure: '°',
            secondName: 'Span:',
            secondMeasure: 'mm',
            thirdName: 'Rise:',
            thirdMeasure: 'mm',
            but: true,
            a: 0,
            s: 0,
            rise: 0,
            ar: 0,
            m: 0,
            rad: 0,
            g: 0,
            h: 0,
            t: 0
        }
    },
    methods: {
        async radiusgirth(){
                this.rad = document.getElementById("7").value;
                this.g = document.getElementById("8").value;
                this.h = document.getElementById("height4").value;
                this.t = document.getElementById("thickness4").value;
                this.a = this.g / this.rad;
                this.s = 2 * this.rad * Math.sin(this.a / 2);
                this.rise = this.rad - 0.5 * Math.sqrt(4 * this.rad * this.rad - this.s * this.s);
                this.ar = (this.h/1000) * (this.g/1000);
                this.m = this.ar * this.t * 2.5;
                this.a = Math.round((this.a * 180)/Math.PI);
                this.s = Math.round(this.s);
                this.rise = Math.round(this.rise);
                this.ar = this.ar.toFixed(2);
                this.m = this.m.toFixed(2);
                this.but = false;
                document.getElementById('button4').style.visibility = "hidden"
            }
    }
}
</script>

<style scoped>
table {
    width: 5%;
    background: #bee0c5;
    position: absolute;
    left: 36%;
    top: 35%
}
</style>
<template>
<table>
            <tr>
                <td>
                    Height:
                </td>
                <td>
                    <input id="height2" size="1">
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
                    <input id="thickness2" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Span:
                </td>
                <td>
                    <input id="3" size="1">
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
                    <input id="4" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    <button id="button2" @click="spanradius()">Calculate!</button>
                </td>
            </tr>
        </table>
            <ResultTables
            v-if="but == false"
            :firstName="firstName"
            :firstValue="rise"
            :firstMeasure="firstMeasure"
            :secondName="secondName"
            :secondValue="a"
            :secondMeasure="secondMeasure"
            :thirdName="thirdName"
            :thirdValue="g"
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
            firstName: 'Span:',
            firstMeasure: 'mm',
            secondName: 'Angle:',
            secondMeasure: '°',
            thirdName: 'Girth:',
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
        spanradius(){
                this.s = document.getElementById("3").value;
                this.rad = document.getElementById("4").value;
                this.h = document.getElementById("height2").value;
                this.t = document.getElementById("thickness2").value;
                this.rise = this.rad - 0.5 * Math.sqrt(4 * this.rad * this.rad - this.s * this.s);
                this.a = 2 * Math.asin(this.s / (2 * this.rad));
                this.g = this.rad * this.a;
                this.ar = (this.h/1000) * (this.g/1000);
                this.m = this.ar * this.t * 2.5;
                this.rise = Math.round(this.rise);
                this.a = Math.round((this.a * 180)/Math.PI);
                this.g = Math.round(this.g);
                this.ar = this.ar.toFixed(2);
                this.m = this.m.toFixed(2);
                this.but = false;
                document.getElementById('button2').style.visibility = "hidden"
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
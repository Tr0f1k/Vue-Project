<template>
<table>
            <tr>
                <td>
                    Height:
                </td>
                <td>
                    <input id="height3" size="1">
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
                    <input id="thickness3" size="1">
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
                    <input id="5" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Rise:
                </td>
                <td>
                    <input id="6" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    <button id="button3" @click="radiusrise()">Calculate!</button>
                </td>
            </tr>
        </table>
            <ResultTables
            v-if="but == false"
            :firstName="firstName"
            :firstValue="s"
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
        radiusrise(){
                this.rad = document.getElementById("5").value;
                this.rise = document.getElementById("6").value;
                this.h = document.getElementById("height3").value;
                this.t = document.getElementById("thickness3").value;
                this.s = 2 * Math.sqrt(this.rise * (2 * this.rad - this.rise));
                this.a = 2 * Math.asin(this.s / (2 * this.rad));
                this.g = this.rad * this.a;
                this.ar = (this.h/1000) * (this.g/1000);
                this.m = this.ar * this.t * 2.5;
                this.s = Math.round(this.s);
                this.a = Math.round((this.a * 180)/Math.PI)
                this.g = Math.round(this.g);
                this.ar = this.ar.toFixed(2);
                this.m = this.m.toFixed(2);
                this.but = false;
                document.getElementById('button3').style.visibility = "hidden"
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
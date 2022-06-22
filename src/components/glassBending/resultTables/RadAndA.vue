<template>
<table>
            <tr>
                <td>
                    Height:
                </td>
                <td>
                    <input id="height5" size="1">
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
                    <input id="thickness5" size="1">
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
                    <input id="9" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Angle:
                </td>
                <td>
                    <input id="10" size="1">
                </td>
                <td>
                    °
                </td>
            </tr>
            <tr>
                <td>
                    <button id="button5" @click="radiusangle()">Calculate!</button>
                </td>
            </tr>
            </table>
            <ResultTables
            v-if="but == false"
            :firstName="firstName"
            :firstValue="s"
            :firstMeasure="firstMeasure"
            :secondName="secondName"
            :secondValue="rise"
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
            secondName: 'Rise:',
            secondMeasure: 'mm',
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
        radiusangle(){
                this.rad = document.getElementById("9").value;
                this.a = document.getElementById("10").value;
                this.h = document.getElementById("height5").value;
                this.t = document.getElementById("thickness5").value;
                this.s = 2 * this.rad * Math.sin(((this.a * Math.PI) / 180)/2);
                this.rise = this.rad - 0.5 * Math.sqrt(4 * this.rad * this.rad - this.s * this.s);
                this.g = this.rad * ((this.a * Math.PI) / 180);
                this.ar = (this.h/1000) * (this.g/1000);
                this.m = this.ar * this.t * 2.5;
                this.s = Math.round(this.s);
                this.rise = Math.round(this.rise);
                this.g = Math.round(this.g);
                this.ar = this.ar.toFixed(2);
                this.m = this.m.toFixed(2);
                console.log(this.rad, this.a, this.h, this.t, this.s, this.rise, this.g, this.ar, this.m);
                this.but = false;
                document.getElementById('button5').style.visibility = "hidden"
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
<template>
<table id="table1" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 35%">
                <tr>
                    <td>
                        Height:
                    </td>
                    <td>
                        <input id="height1" size="1">
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
                        <input id="thickness1" size="1">
                    </td>
                    <td>
                        mm
                    </td>
                </tr>
                <tr>
                <td>
                    Span:
                </td>
                <td style="width: 10%">
                    <input id="1" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    Rise:
                </td>
                <td style="width: 10%">
                    <input id="2" size="1">
                </td>
                <td>
                    mm
                </td>
            </tr>
            <tr>
                <td>
                    <button id="button1" @click="spanrise()">Calculate!</button>
                </td>
            </tr>
        </table>
            <ResultTables
            v-if="but == false"
            :firstName="firstName"
            :firstValue="rad"
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
        spanrise(){
                this.s = document.getElementById("1").value;
                this.rise = document.getElementById("2").value;
                this.h = document.getElementById("height1").value;
                this.t = document.getElementById("thickness1").value;
                this.rad = (this.s * this.s + 4 * this.rise * this.rise) / (8 * this.rise);
                this.a = 2 * Math.asin(this.s / (2 * this.rad));
                this.g = this.rad * this.a;
                this.ar = (this.h/1000) * (this.g/1000);
                this.m = this.ar * this.t * 2.5;
                this.rad = Math.round(this.rad);
                this.a = Math.round((this.a * 180)/Math.PI);
                this.g = Math.round(this.g);
                this.ar = this.ar.toFixed(2);
                this.m = this.m.toFixed(2);
                this.but = false;
                document.getElementById('button1').style.visibility = "hidden"
            }
    }
}
</script>
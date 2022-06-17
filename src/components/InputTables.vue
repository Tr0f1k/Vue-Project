<template>
<button @click="openTables()">Press me!</button>
<table id="table1" style="width: 5%; background: #bee0c5; visibility: hidden; position: absolute; left: 36%; top: 25%">
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
        <table id="table2" style="width: 5%; background: #bee0c5; visibility: hidden; position: absolute; left: 36%; top: 25%">
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
        <table id="table3" style="width: 5%; background: #bee0c5; visibility: hidden; position: absolute; left: 36%; top: 25%">
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
        <table id="table4" style="width: 5%; background: #bee0c5; visibility: hidden; position: absolute; left: 36%; top: 25%">
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
        <table id="table5" style="width: 5%; background: #bee0c5; visibility: hidden; position: absolute; left: 36%; top: 25%">
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
                    <table id="1resultTable" style="width: 9.8%; background: #bee0c5; visibility: hidden; position: absolute; top:36%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        Radius:
                    </td>
                    <td id="1rad" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Angle:
                    </td>
                    <td id="1a" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Girth:
                    </td>
                    <td id="1g" style="size: 25%">

                    </td>
                </tr>
        </table>
        <table id="2resultTable" style="width: 9.8%; background: #bee0c5; visibility: hidden; position: absolute; top:36%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        Rise:
                    </td>
                    <td id="2rise" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Angle:
                    </td>
                    <td id="2a" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Girth:
                    </td>
                    <td id="2g" style="size: 25%">

                    </td>
                </tr>
        </table>
        <table id="3resultTable" style="width: 9.8%; background: #bee0c5; visibility: hidden; position: absolute; top:36%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        Span:
                    </td>
                    <td id="3span" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Angle:
                    </td>
                    <td id="3a" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Girth:
                    </td>
                    <td id="3g" style="size: 25%">

                    </td>
                </tr>
        </table>
        <table id="4resultTable" style="width: 9.8%; background: #bee0c5; visibility: hidden; position: absolute; top:36%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        Angle:
                    </td>
                    <td id="4a" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Span:
                    </td>
                    <td id="4s" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Rise:
                    </td>
                    <td id="4rise" style="size: 25%">

                    </td>
                </tr>
        </table>
        <table id="5resultTable" style="width: 9.8%; background: #bee0c5; visibility: hidden; position: absolute; top:36%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        Span:
                    </td>
                    <td id="5s" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Rise:
                    </td>
                    <td id="5rise" style="size: 25%">

                    </td>
                </tr>
                <tr>
                    <td>
                        Girth:
                    </td>
                    <td id="5g" style="size: 25%">

                    </td>
                </tr>
        </table>
        <table id="tableArea1" style="width: 10%; visibility: hidden; background: #bee0c5; position: absolute; top: 60%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td id="area1">

                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td id="weight1">

                    </td>
                </tr>
            </table>
            <table id="tableArea2" style="width: 10%; visibility: hidden; background: #bee0c5; position: absolute; top: 60%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td id="area2">

                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td id="weight2">

                    </td>
                </tr>
            </table>
            <table id="tableArea3" style="width: 10%; visibility: hidden; background: #bee0c5; position: absolute; top: 60%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td id="area3">

                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td id="weight3">

                    </td>
                </tr>
            </table>
            <table id="tableArea4" style="width: 10%; visibility: hidden; background: #bee0c5; position: absolute; top: 60%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td id="area4">

                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td id="weight4">

                    </td>
                </tr>
            </table>
            <table id="tableArea5" style="width: 10%; visibility: hidden; background: #bee0c5; position: absolute; top: 60%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td id="area5">

                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td id="weight5">

                    </td>
                </tr>
            </table>
            <table id="tableAngle" align="center" width="99%" style="visibility: hidden; background: #bee0c5; position: absolute; top: 75%; text-align: center;">
                <tr>
                    <td style="font-size: 20px; color: red" colspan="2" id="angle">

                    </td>
                </tr>
            </table>
</template>

<script>
import HelloWorld from './HelloWorld'
export default {
    name:'InputTables',
    components: {
        HelloWorld
    },
    props: {
        id: String,
    },
    methods: {
        openTables () {
            console.log(this.id)
            switch(this.id){
                    case "default":
                        document.getElementById('table1').style.visibility = "hidden";
                        document.getElementById('table2').style.visibility = "hidden";
                        document.getElementById('table3').style.visibility = "hidden";
                        document.getElementById('table4').style.visibility = "hidden";
                        document.getElementById('table5').style.visibility = "hidden";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button1').style.visibility = "hidden";
                        document.getElementById('button2').style.visibility = "hidden";
                        document.getElementById('button3').style.visibility = "hidden";
                        document.getElementById('button4').style.visibility = "hidden";
                        document.getElementById('button5').style.visibility = "hidden";
                        break;

                    case "sAndRise":
                        document.getElementById('table1').style.visibility = "visible";
                        document.getElementById('table2').style.visibility = "hidden";
                        document.getElementById('table3').style.visibility = "hidden";
                        document.getElementById('table4').style.visibility = "hidden";
                        document.getElementById('table5').style.visibility = "hidden";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button1').style.visibility = "visible";
                        break;

                    case "sAndRad":
                        document.getElementById('table1').style.visibility = "hidden";
                        document.getElementById('table2').style.visibility = "visible";
                        document.getElementById('table3').style.visibility = "hidden";
                        document.getElementById('table4').style.visibility = "hidden";
                        document.getElementById('table5').style.visibility = "hidden";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button2').style.visibility = "visible";
                        break;

                    case "radAndRise":
                        document.getElementById('table1').style.visibility = "hidden";
                        document.getElementById('table2').style.visibility = "hidden";
                        document.getElementById('table3').style.visibility = "visible";
                        document.getElementById('table4').style.visibility = "hidden";
                        document.getElementById('table5').style.visibility = "hidden";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button3').style.visibility = "visible";
                        break;

                    case "radAndG":
                        document.getElementById('table1').style.visibility = "hidden";
                        document.getElementById('table2').style.visibility = "hidden";
                        document.getElementById('table3').style.visibility = "hidden";
                        document.getElementById('table4').style.visibility = "visible";
                        document.getElementById('table5').style.visibility = "hidden";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button4').style.visibility = "visible";
                        break;

                    case "radAndA":
                        document.getElementById('table1').style.visibility = "hidden";
                        document.getElementById('table2').style.visibility = "hidden";
                        document.getElementById('table3').style.visibility = "hidden";
                        document.getElementById('table4').style.visibility = "hidden";
                        document.getElementById('table5').style.visibility = "visible";
                        document.getElementById('1resultTable').style.visibility = "hidden";
                        document.getElementById('2resultTable').style.visibility = "hidden";
                        document.getElementById('3resultTable').style.visibility = "hidden";
                        document.getElementById('4resultTable').style.visibility = "hidden";
                        document.getElementById('5resultTable').style.visibility = "hidden";
                        document.getElementById('tableArea1').style.visibility = "hidden";
                        document.getElementById('tableArea2').style.visibility = "hidden";
                        document.getElementById('tableArea3').style.visibility = "hidden";
                        document.getElementById('tableArea4').style.visibility = "hidden";
                        document.getElementById('tableArea5').style.visibility = "hidden";
                        document.getElementById('tableAngle').style.visibility = "hidden";
                        document.getElementById('button5').style.visibility = "visible";
                        break;
                }
        },
            spanrise(){
                var s = document.getElementById("1").value;
                var rise = document.getElementById("2").value;
                var h = document.getElementById("height1").value;
                var t = document.getElementById("thickness1").value;
                var rad = (s * s + 4 * rise * rise) / (8 * rise);
                var a = 2 * Math.asin(s / (2 * rad));
                var g = rad * a;
                var ar = (h/1000) * (g/1000);
                var m = ar * t * 2.5;
                console.log (s, rise, h, t, rad, a, g, ar, m)
                document.getElementById('1resultTable').style.visibility = "visible";
                document.getElementById('1rad').innerHTML = Math.round(rad) + " mm";
                document.getElementById('1a').innerHTML = Math.round((a * 180)/Math.PI) + "°";
                document.getElementById('1g').innerHTML = Math.round(g) + " mm";
                document.getElementById('tableArea1').style.visibility = "visible";
                document.getElementById('area1').innerHTML = ar.toFixed(2) + " m²";
                document.getElementById('weight1').innerHTML = m.toFixed(2) + " kg";
                document.getElementById('button1').style.visibility = "hidden";
                if ((a * 180)/Math.PI > 90){
                    document.getElementById('tableAngle').style.visibility = "visible";
                    document.getElementById('angle').innerHTML = "WARNING! ANGLE IS > 90°!";
                }
                /*document.write("radius = " + Math.round(rad) + ", angle = " + Math.round((a * 180)/Math.PI) + ", girth = " + Math.round(g));*/
            },
    
            spanradius(){
                var s = document.getElementById("3").value;
                var rad = document.getElementById("4").value;
                var h = document.getElementById("height2").value;
                var t = document.getElementById("thickness2").value;
                var rise = rad - 0.5 * Math.sqrt(4 * rad * rad - s * s);
                var a = 2 * Math.asin(s / (2 * rad));
                var g = rad * a;
                var ar = (h/1000) * (g/1000);
                var m = ar * t * 2.5;
                document.getElementById('2resultTable').style.visibility = "visible";
                document.getElementById('2rise').innerHTML = Math.round(rise) + " mm";
                document.getElementById('2a').innerHTML = Math.round((a * 180)/Math.PI) + "°";
                document.getElementById('2g').innerHTML = Math.round(g) + " mm";
                document.getElementById('tableArea2').style.visibility = "visible";
                document.getElementById('area2').innerHTML = ar.toFixed(2) + " m²";
                document.getElementById('weight2').innerHTML = m.toFixed(2) + " kg";
                document.getElementById('button2').style.visibility = "hidden";
                if ((a * 180)/Math.PI > 90){
                    document.getElementById('tableAngle').style.visibility = "visible";
                    document.getElementById('angle').innerHTML = "WARNING! ANGLE IS > 90°!";
                }
                /*document.write("rise = " + Math.round(rise) + ", angle = " + Math.round((a * 180)/Math.PI) + ", girth = " + Math.round(g));*/
            },
    
            radiusrise(){
                var rad = document.getElementById("5").value;
                var rise = document.getElementById("6").value;
                var h = document.getElementById("height3").value;
                var t = document.getElementById("thickness3").value;
                var s = 2 * Math.sqrt(rise * (2 * rad - rise));
                var a = 2 * Math.asin(s / (2 * rad));
                var g = rad * a;
                var ar = (h/1000) * (g/1000);
                var m = ar * t * 2.5;
                document.getElementById('3resultTable').style.visibility = "visible";
                document.getElementById('3span').innerHTML = Math.round(s);
                document.getElementById('3a').innerHTML = Math.round((a * 180)/Math.PI);
                document.getElementById('3g').innerHTML = Math.round(g);
                document.getElementById('tableArea3').style.visibility = "visible";
                document.getElementById('area3').innerHTML = ar.toFixed(2) + " m²";
                document.getElementById('weight3').innerHTML = m.toFixed(2) + " kg";
                document.getElementById('button3').style.visibility = "hidden";
                if ((a * 180)/Math.PI > 90){
                    document.getElementById('tableAngle').style.visibility = "visible";
                    document.getElementById('angle').innerHTML = "WARNING! ANGLE IS > 90°!";
                }
                /*document.write("span = " + Math.round(s) + ", angle = " + Math.round((a * 180)/Math.PI) + ", girth = " + Math.round(g));*/
            },
    
            radiusgirth(){
                var rad = document.getElementById("7").value;
                var g = document.getElementById("8").value;
                var h = document.getElementById("height4").value;
                var t = document.getElementById("thickness4").value;
                var a = g / rad;
                var s = 2 * rad * Math.sin(a / 2);
                var rise = rad - 0.5 * Math.sqrt(4 * rad * rad - s * s);
                var ar = (h/1000) * (g/1000);
                var m = ar * t * 2.5;
                document.getElementById('4resultTable').style.visibility = "visible";
                document.getElementById('4a').innerHTML = Math.round((a * 180)/Math.PI) + "°";
                document.getElementById('4s').innerHTML = Math.round(s) + " mm";
                document.getElementById('4rise').innerHTML = Math.round(rise) + " mm";
                document.getElementById('tableArea4').style.visibility = "visible";
                document.getElementById('area4').innerHTML = ar.toFixed(2) + " m²";
                document.getElementById('weight4').innerHTML = m.toFixed(2) + " kg";
                document.getElementById('button4').style.visibility = "hidden";
                if ((a * 180)/Math.PI > 90){
                    document.getElementById('tableAngle').style.visibility = "visible";
                    document.getElementById('angle').innerHTML = "WARNING! ANGLE IS > 90°!";
                }
                /*document.write("angle = " + Math.round((a * 180)/Math.PI) + ", span = " + Math.round(s) + ", rise = " + Math.round(rise));*/
            },
    
            radiusangle(){
                var rad = document.getElementById("9").value;
                var a = document.getElementById("10").value;
                var h = document.getElementById("height5").value;
                var t = document.getElementById("thickness5").value;
                var s = 2 * rad * Math.sin(((a * Math.PI) / 180)/2);
                var rise = rad - 0.5 * Math.sqrt(4 * rad * rad - s * s);
                var g = rad * ((a * Math.PI) / 180);
                var ar = (h/1000) * (g/1000);
                var m = ar * t * 2.5;
                document.getElementById('5resultTable').style.visibility = "visible";
                document.getElementById('5s').innerHTML = Math.round(s) + " mm";
                document.getElementById('5rise').innerHTML = Math.round(rise) + " mm";
                document.getElementById('5g').innerHTML = Math.round(g) + " mm";
                document.getElementById('tableArea5').style.visibility = "visible";
                document.getElementById('area5').innerHTML = ar.toFixed(2) + " m²";
                document.getElementById('weight5').innerHTML = m.toFixed(2) + " kg";
                document.getElementById('button5').style.visibility = "hidden";
                if (a > 90){
                    document.getElementById('tableAngle').style.visibility = "visible";
                    document.getElementById('angle').innerHTML = "WARNING! ANGLE IS > 90°!";
                }
                /*document.write("span = " + Math.round(s) + ", rise = " + Math.round(rise) + ", girth = " + Math.round(g));*/
            }
    }
}
</script>

<style scoped>
</style>
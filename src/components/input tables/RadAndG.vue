<template>
<table id="table4" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 25%">
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
        <table id="tableAngle" align="center" width="99%" style="visibility: hidden; background: #bee0c5; position: absolute; top: 75%; text-align: center;">
                <tr>
                    <td style="font-size: 20px; color: red" colspan="2" id="angle">

                    </td>
                </tr>
            </table>
</template>

<script>
export default {
    name: "RadAndG",
    methods: {
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
            }
    }
}
</script>
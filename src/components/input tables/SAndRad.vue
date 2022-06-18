<template>
<table id="table2" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 25%">
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
            <table id="tableAngle" align="center" width="99%" style="visibility: hidden; background: #bee0c5; position: absolute; top: 75%; text-align: center;">
                <tr>
                    <td style="font-size: 20px; color: red" colspan="2" id="angle">

                    </td>
                </tr>
            </table>
</template>

<script>
export default {
    name: "SAndRad",
    methods: {
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
            }
    }
}
</script>
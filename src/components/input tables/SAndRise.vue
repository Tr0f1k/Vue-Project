<template>
<table id="table1" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 25%">
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
            <table id="tableAngle" align="center" width="99%" style="visibility: hidden; background: #bee0c5; position: absolute; top: 75%; text-align: center;">
                <tr>
                    <td style="font-size: 20px; color: red" colspan="2" id="angle">

                    </td>
                </tr>
            </table>
</template>

<script>
export default {
    name: "SAndRise",
    methods: {
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
            }
    }
}
</script>
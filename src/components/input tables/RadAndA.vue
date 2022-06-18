<template>
<table id="table5" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 25%">
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
export default {
    name: "RadAndA",
    methods: {
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
            }
    }
}
</script>
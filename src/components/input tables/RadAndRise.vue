<template>
<table id="table3" style="width: 5%; background: #bee0c5; position: absolute; left: 36%; top: 25%">
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
        <table id="tableAngle" align="center" width="99%" style="visibility: hidden; background: #bee0c5; position: absolute; top: 75%; text-align: center;">
                <tr>
                    <td style="font-size: 20px; color: red" colspan="2" id="angle">

                    </td>
                </tr>
            </table>
</template>

<script>
export default {
    name: "RadAndRise",
    methods: {
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
            }
    }
}
</script>
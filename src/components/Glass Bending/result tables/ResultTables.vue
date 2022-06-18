<template>
            <table style="width: 9.8%; background: #bee0c5; position: absolute; top:46%; left: 36%; table-layout: fixed;">
                <tr>
                    <td>
                        {{firstName}}
                    </td>
                    <td id="5s" style="size: 25%">
                        {{firstValue}} {{firstMeasure}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{secondName}}
                    </td>
                    <td id="5rise" style="size: 25%">
                        {{secondValue}} {{secondMeasure}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{thirdName}}
                    </td>
                    <td id="5g" style="size: 25%">
                        {{thirdValue}} {{thirdMeasure}}
                    </td>
                </tr>
        </table>
            <table style="width: 10%; background: #bee0c5; position: absolute; top: 70%; left: 55%">
                <tr>
                    <td>
                        Area:
                    </td>
                    <td>
                        {{areaValue}} m²
                    </td>
                </tr>
                <tr>
                    <td>
                        Weight:
                    </td>
                    <td>
                        {{weightValue}} kg
                    </td>
                </tr>
            </table>
</template>

<script>
    export default {
        name: "ResultTables",
        props: {
            firstName: String,
            firstValue: Number,
            firstMeasure: String,
            secondName: String,
            secondValue: Number,
            secondMeasure: String,
            thirdName: String,
            thirdValue: Number,
            thirdMeasure: String,
            areaValue: String,
            weightValue: String
        }
    }
</script>
<template>
            <table class="resultTable">
                <tr>
                    <td>
                        {{firstName}}
                    </td>
                    <td class="cell">
                        {{firstValue}} {{firstMeasure}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{secondName}}
                    </td>
                    <td class="cell">
                        {{secondValue}} {{secondMeasure}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{thirdName}}
                    </td>
                    <td class="cell">
                        {{thirdValue}} {{thirdMeasure}}
                    </td>
                </tr>
        </table>
            <table class="areaWeight">
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

<style scoped>
.resultTable {
    width: 9.8%;
    background: #bee0c5;
    position: absolute;
    top:46%;
    left: 36%;
    table-layout: fixed
}

.areaWeight {
    width: 10%;
    background: #bee0c5;
    position: absolute;
    top: 70%;
    left: 55%
}

.cell {
    size: 25%
}
</style>
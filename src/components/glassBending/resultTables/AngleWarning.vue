<template>
    <table>
        <tr>
            <td style="font-size: 20px; color: red" colspan="2" id="angle">
                WARNING! ANGLE IS > 90°!
            </td>
        </tr>
    </table>
</template>

<script>
export default {
    name: "AngleWarning",
}
</script>

<style scoped>
table {
    background: #bee0c5;
    position: absolute;
    top: 85%;
    text-align: center;
    width: 99%;
    align-items: "center"
}
</style>
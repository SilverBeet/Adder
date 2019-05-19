<template>
    <div class="tableWrapper">
        <table>
            <thead>
                <tr>
                    <th>Navn</th>
                    <th>Timer</th>
                </tr>
            </thead>
            <tbody class="tbody-data">
                <tr :id="i" v-for="(person, i) in persons" :key="i">
                    <td>{{person.name}}</td>
                    <td>{{person.hours}}</td>
                </tr>
                <tr>
                    <td colspan="2">Total timer:<span class="total">{{addRows(persons)}}</span> </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {

        name: 'table-app',

        props: ['persons'],

        methods: {
            addRows(arr) {
                let sum = 0;
                arr.map((col, i) => sum += Number(arr[i].hours));
                return sum;
            }
        }
    }
</script>

<style scope="css">
    table {
        width: 550px;
        margin: 50px auto;
        color: rgba(165, 189, 30, 0.569);

        border-collapse: collapse;
        font-size: 15px;
    }

    .total {
        float: right;
    }
    .totalText {
        text-align: left;
    }

    th,
    td {
        padding: 10px;
        text-align: left;
        border: 1px solid rgba(165, 189, 30, 0.569);
    }
</style>
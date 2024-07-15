<script></script>

<template>
    <div class="container">

<form class="form-style">
    <h2>BMI測驗</h2>
    <label for="my_height">
        <span>身高:</span>
        <input type="number" class="my_height" id="my_height"><span>cm</span>
    </label>
    <label for="my_weight">
        <span>體重:</span>
        <input type="number" class="my_weight" id="my_weight"><span>kg</span>
    </label>

    <button id="my_btn" class="my_btn" type="button">開始計算</button>

    <div class="my-span">
        <span>您的BMI值:</span><span class="show_01"></span>
    </div>

</form>

<table class="my-table">
    <tr>

        <th>顯示範圍</th>
        <th>身體質量指數(BMI)
            (kg/m2)</th>

    </tr>
    <tr id="thin">

        <td>BMI ＜ 18.5 </td>
        <td>「體重過輕」，需要多運動，均衡飲食，以增加體能，維持健康！</td>

    </tr>
    <tr id="normal">

        <td>18.5≦BMI＜24</td>
        <td>恭喜！「健康體重」，要繼續保持！</td>

    </tr>

    <tr id="heavy">

        <td>24≦BMI＜27</td>
        <td>「體重過重」了，要小心囉，趕快力行「健康體重管理」！</td>

    </tr>

    <tr id="fat">

        <td>27≦BMI</td>
        <td>啊～「肥胖」，需要立刻力行「健康體重管理」囉！</td>

    </tr>


</table>

</div>
</template>

<style>
.form-style {
            width: 200px;
            margin: auto;
            margin-top: 50px;
        }

        .my_btn {
            margin-top: 10px;
        }

        .my-span {
            margin-top: 10px;
        }

        .my-table {
            margin: auto;
            margin-top: 10px;
        }

        table,
        th,
        td {
            border: 1px solid black;
            border-collapse: collapse;


        }
</style>
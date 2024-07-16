<script>
export default {
    data() {
        return {
            peopleheight: 0,
            peopleweight: 0,
            result: null,
        };
    },
    methods: {
        bmical() {
            const height = parseFloat(this.peopleheight);
            const weight = parseFloat(this.peopleweight);
            if (height > 0 && weight > 0) {
                this.result = (weight / ((height / 100) * (height / 100))).toFixed(2);
            } else {
                this.result = null;
            }
        },
        clearbmi() {
            this.peopleheight = 0;
            this.peopleweight = 0;
            this.result = null;
        },
    },
};
</script>

<template>
    <div class="container">
        <form class="form-style w-[200px] mt-[50px]">
            <h2>BMI測驗</h2>
            <label for="my_height">
                <span>身高:</span>
                <input v-model="peopleheight" type="number" class="my_height" id="my_height"><span>cm</span>
            </label>
            <label for="my_weight">
                <span>體重:</span>
                <input v-model="peopleweight" type="number" class="my_weight" id="my_weight"><span>kg</span>
            </label>

            <button @click="bmical" id="my_btn" class="my_btn mt-[10px] border" type="button">開始計算</button>
            <button @click="clearbmi" id="my_btn" class="my_btn mt-[10px] border" type="button">清除計算</button>

            <div class="my-span mt-[10px]" v-if="result !== null">
                <span>您的BMI值:</span><span class="show_01">{{ result }}</span>
            </div>
        </form>

        <table class="my-table mt-[10px]">
            <tr>
                <th>顯示範圍</th>
                <th>身體質量指數(BMI) (kg/m2)</th>
            </tr>
            <tr id="thin" v-if="result !== null && result < 18.5">
                <td class="yellow">BMI ＜ 18.5 </td>
                <td class="yellow">「體重過輕」，需要多運動，均衡飲食，以增加體能，維持健康！</td>
            </tr>
            <tr id="thin" v-else>
                <td>BMI ＜ 18.5 </td>
                <td>「體重過輕」，需要多運動，均衡飲食，以增加體能，維持健康！</td>
            </tr>
            <tr id="normal" v-if="result !== null && 18.5 <= result && result < 24">
                <td class="yellowgreen">18.5≦BMI＜24</td>
                <td class="yellowgreen">恭喜！「健康體重」，要繼續保持！</td>
            </tr>
            <tr id="normal" v-else>
                <td>18.5≦BMI＜24</td>
                <td>恭喜！「健康體重」，要繼續保持！</td>
            </tr>
            <tr id="heavy" v-if="result !== null && 24 <= result && result < 27">
                <td class="orange">24≦BMI＜27</td>
                <td class="orange">「體重過重」了，要小心囉，趕快力行「健康體重管理」！</td>
            </tr>
            <tr id="heavy" v-else>
                <td>24≦BMI＜27</td>
                <td>「體重過重」了，要小心囉，趕快力行「健康體重管理」！</td>
            </tr>
            <tr id="fat" v-if="result !== null && result >= 27">
                <td class="red">27≦BMI</td>
                <td class="red">啊～「肥胖」，需要立刻力行「健康體重管理」囉！</td>
            </tr>
            <tr id="fat" v-else>
                <td>27≦BMI</td>
                <td>啊～「肥胖」，需要立刻力行「健康體重管理」囉！</td>
            </tr>
        </table>
    </div>
</template>

<style>
.form-style {
    margin: auto;
}

.my-table {
    margin: auto;
}

table,
th,
td {
    border: 1px solid black;
    border-collapse: collapse;
}

.yellow {
    background-color: yellow;
}

.yellowgreen {
    background-color: yellowgreen;
}

.orange {
    background-color: orange;
}

.red {
    background-color: red;
}
</style>
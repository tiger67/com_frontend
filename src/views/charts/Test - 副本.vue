<template>
    <section class="chart-container">
        <h3>{{title}}</h3>
        <div>
            <form>
                <div>
                    <label for="username">用户名</label>
                    <input type="text" id="username" name="username">
                </div>
                <div>
                    <label for="username">密码</label>
                    <input type="text" id="password" name="password">
                </div>
                <div>
                    <div class="submit-btn">提交</div>
                </div>
            </form>
        </div>
    </section>
</template>
<script>
import axios from "axios"
export default {
    data() {
        return {
            title: "登录页面",
        }
    },
    methods: {

    },
    mounted: function() {
        /*axios({ method: "get", url: "http://localhost:9000/test", params: { name: '三季度数据的技术' } }).then((res) => { console.log(res); }) var fdata = new FormData(); fdata.append("name", "52525252");*/

        axios.defaults.headers.post['Content-Type'] = 'text/plain;charset=UTF-8';
        axios({
            method: "post",
            url: "http://localhost:9000/login",
            data: { name: "admin", password: "123456" }
        }).then((res) => {
            console.log(res);
        }).catch(() => {})
    },
    updated: function() {
        this.drawCharts()
    }
}
</script>
<style scoped>
.chart-container {
    width: 100%;
    float: left;
}

.el-col {
    padding: 30px 20px;
}
</style>
<template>
    <section class="layout">
        <div class="from-con">
            <form>
                <div class="input-line">
                    <label for="username">用户名：</label>
                    <input type="text" id="username" v-model="name">
                </div>
                <div class="input-line">
                    <label for="username">密码：</label>
                    <input type="password" id="password" v-model="password">
                </div>
                <div class="input-line">
                    <input type="submit" class="submit-btn" value="登录" @click.prevent="login" />
                    <router-link to="/register">去注册</router-link>
                </div>
            </form>
        </div>
    </section>
</template>
<style scoped>
.layout {
    width: 800px;
    margin: 20px auto;
    color: #333;
    font-size: 14px;
}

.login-title {
    font-size: 25px;
    line-height: 40px;
}

.input-line {
    height: 35px;
    margin: 12px 0;
}

.input-line>label {
    display: inline-block;
    width: 100px;
    text-align: right;
    font-size: 16px;
    margin-left: -100px;
}

input {
    width: 200px;
    height: 32px;
    box-sizing: border-box;
    padding: 2px 5px;
    line-height: 28px;
    font-size: 16px;
    border: 1px solid #ccc;
    outline: none;
    color: #333;
}

.submit-btn {
    width: 100px;
    height: 36px;
    color: #fff;
    font-size: 16px;
    letter-spacing: 1px;
    background: #3385ff;
    border-bottom: 1px solid #2d78f4;
    outline: medium;
    -webkit-appearance: none;
    -webkit-border-radius: 0;
    cursor: pointer;
}

.from-con {

    padding-left: 130px;
    border: 1px solid #ddd;
    width: 280px;
    margin: 50px auto;
    padding-top: 30px;
    padding-bottom: 30px;
}
</style>
<script>
import axios from "axios";
export default {
    data() {
        return {
            title: "登录",
            name: '',
            password: ''
        }
    },
    methods: {
        login: function() {
            console.log(this.name);
            console.log(this.password);
            /* axios({
                 method: "post",
                 url: "http://localhost:9000/login",
                 data: { name: "admin", password: "123456" }
             }).then((res) => {
                 console.log(res);
             }).catch(() => {})*/
        }

    },
    mounted: function() {


    },

}
</script>
<style scoped>
</style>
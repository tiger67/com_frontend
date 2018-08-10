<template>
    <section class="layout">
        <div class="from-con">
            <form>
                <div class="input-line">
                    <input type="text" placeholder="手机号" v-model="telephone">
                </div>
                <div class="input-line">
                    <input type="text" v-model="number">
                </div>
                <div class="input-line">
                    <input type="submit" placeholder="输入6位短信验证码" class="submit-btn" value="注册" @click.prevent="login" />
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
    min-height: 35px;
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
    width: 260px;
    height: 32px;
    box-sizing: border-box;
    padding: 2px 5px;
    line-height: 28px;
    font-size: 16px;
    border: none;
    border-bottom: 1px solid #ccc;
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
    margin-top: 30px;
}

.from-con {
    border: 1px solid transparent;
    width: 280px;
    margin: 50px auto;
    padding: 30px;
}
</style>
<script>
import axios from "axios"
export default {
    data() {
        return {
            title: "登录",
            telephone: '',
            number: ''
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
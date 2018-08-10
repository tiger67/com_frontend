<template>
    <el-form :model="ruleForm2" :rules="rules2" ref="ruleForm2" label-position="left" label-width="0px" class="demo-ruleForm login-container">
        <h3 class="title">系统登录</h3>
        <el-form-item prop="account">
            <el-input type="text" v-model="ruleForm2.account" auto-complete="off" placeholder="账号"></el-input>
        </el-form-item>
        <el-form-item prop="checkPass">
            <el-input type="password" v-model="ruleForm2.checkPass" auto-complete="off" placeholder="密码"></el-input>
        </el-form-item>
        <el-checkbox v-model="checked" checked class="remember">记住密码</el-checkbox>
        <el-form-item style="width:100%;">
            <el-button type="primary" style="width:100%;" @click.native.prevent="handleSubmit2" :loading="logining">登录</el-button>
            <!--<el-button @click.native.prevent="handleReset2">重置</el-button>-->
        </el-form-item>
    </el-form>
</template>
<script>
import { requestLogin, login, gettest } from '../api/api';
import axios from 'axios';
console.dir(axios);

export default {
    data() {
        return {
            logining: false,
            ruleForm2: {
                account: 'admin',
                checkPass: '123456'
            },
            rules2: {
                account: [
                    { required: true, message: '请输入账号', trigger: 'blur' },
                    //{ validator: validaePass }
                ],
                checkPass: [
                    { required: true, message: '请输入密码', trigger: 'blur' },
                    //{ validator: validaePass2 }
                ]
            },
            checked: true
        };
    },
    methods: {
        handleReset2() {
            this.$refs.ruleForm2.resetFields();
        },
        handleSubmit2(ev) {
            var xhr = new XMLHttpRequest();
            xhr.open("post", "http://localhost:9000/login");
            xhr.onload = function() {
                console.log(JSON.parse(xhr.responseText));
            }

            xhr.send({ name: "sjdjs" });
            // axios.defaults.baseURL = 'http//localhost:9000';
            //axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;
            /* axios.defaults.headers.get['Content-Type'] = 'application/x-www-form-urlencoded';
             axios.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded';*/
            axios.get("http//localhost:9000/test").then((res) => {
                console.log(res)
            })
            /* gettest().then((res) => { console.log(res) })*/
            // login({ name: "sdsd", password: "sjkdjksahd" }).then(function(response) { console.log(response) })
        }
    }
}
</script>
<style lang="scss" scoped>
.login-container {
    /*box-shadow: 0 0px 8px 0 rgba(0, 0, 0, 0.06), 0 1px 0px 0 rgba(0, 0, 0, 0.02);*/
    -webkit-border-radius: 5px;
    border-radius: 5px;
    -moz-border-radius: 5px;
    background-clip: padding-box;
    margin: 180px auto;
    width: 350px;
    padding: 35px 35px 15px 35px;
    background: #fff;
    border: 1px solid #eaeaea;
    box-shadow: 0 0 25px #cac6c6;
    .title {
        margin: 0px auto 40px auto;
        text-align: center;
        color: #505458;
    }
    .remember {
        margin: 0px 0px 35px 0px;
    }
}
</style>
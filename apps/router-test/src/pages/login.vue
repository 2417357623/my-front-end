<template>
    <form @submit.prevent="login">
        <label for="username">Username</label>
        <input v-model="form.username" name="username" type="text">
        
        <label for="password">Password</label>
        <input v-model="form.password" name="password" type="password">
        
        <button type="submit">Login</button>
    </form>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();
const form = ref({
    username: "",
    password: ""
});

function login() {
    // 登录逻辑，比如验证用户名和密码
    if (form.value.username && form.value.password) {
        console.log("Logging in with:", form.value);
        window.user= form.value.username;
        // 假设登录成功，重定向到首页
        router.push({ name: 'protect' });
    } else {
        console.error("Please enter both username and password");
    }
}
</script>

<style scoped>
/* 这里可以添加一些样式 */
</style>

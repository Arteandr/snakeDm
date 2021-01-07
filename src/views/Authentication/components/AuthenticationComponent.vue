

<template>
    <div class="loginContainer">
        <div class="container">
        <h1>Войти</h1>
        <span>Новый пользователь?<button @click="showRegister">Создать игровой аккаунт</button></span>
        <form>
            <label>
            <input type="text"/>
            <span>Логин</span>
            </label>
            <label>
                <input :type="showPassword ? 'text' : 'password'" /><img :src="showPassword ? eyeoff : eye" @click="switchEye" />
            <span>Пароль</span>
            </label>
            <button class="btn">Войти в аккаунт</button>
        </form>
        </div>
    </div>
</template>

<script>
import eye from "./eye.svg";
import eyeoff from "./eyeoff.svg";

export default {
    name: "AuthenticationComponent",
    data() {
        return {
            eye,
            eyeoff,
            showPassword: false,
        }
    },
    methods: {
        switchEye() {
            this.showPassword = !this.showPassword
        },
        showRegister() {
            this.$emit("show-registration");
        }
    }
}
</script>

<style scoped>
.loginContainer{
  height: 456px;
}
</style>
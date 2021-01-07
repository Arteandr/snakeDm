<template>
    <div class="loginContainer">
        <div class="container">
        <h1>Создать игровой аккаунт</h1>
        <span>У вас уже есть игровой аккаунт?<button @click="showAuth">Войти</button></span>
        <form>
            <label>
            <input type="text">
            <span>Логин</span>
            </label>
            <label>
            <input type="email">
            <span>Электронная почта</span>
            </label>    
            <label>
            <input :type="showPassword ? 'text' : 'password'" /><img :src="showPassword ? eyeoff : eye"  @click="switchEye" />
            <span>Пароль</span>
            </label>
            <button class="btn" >Пройти регистрацию</button>
        </form>
        </div>
    </div>
</template>

<script>
import eye from "./eye.svg";
import eyeoff from "./eyeoff.svg";

export default {
    name: "RegistrationComponent",
    data() {
        return {
            eye,
            eyeoff,
            showPassword: false,
        }
    },
    methods: {
        switchEye() {
            this.showPassword = !this.showPassword;
        },
        showAuth() {
            this.$emit("show-authentication");
        }
    }
}
</script>

<style scoped>
.loginContainer{
  height: 510px;
}
</style>
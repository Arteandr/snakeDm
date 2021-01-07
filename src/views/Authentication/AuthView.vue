<template>
    <div class="authBackground">
        <Auth v-if="showAuth" @show-registration="switchShow(false)" />
        <Register v-else @show-authentication="switchShow(true)" />
    </div>
</template>

<script>
import Auth from "./components/AuthenticationComponent";
import Register from "./components/RegistrationComponent";

export default {
    name: "AuthView",
    data(){ 
        return {
           showAuth: true,
        }
    },
    components: {
        Auth,
        Register
    },
    methods: {
        switchShow(arg) {
            this.showAuth = arg;
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600&display=swap');


*{
  margin: 0;
  -webkit-user-select: none;
  -webkit-user-drag: none;
}
.authBackground{
width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url("./background.png") no-repeat center;
  background-size: cover;
  font-family: 'Open Sans', sans-serif;
}
.loginContainer{
  width: 735px;
  height: 510px;
  display: flex;
  justify-content: center;
  background: rgba(31,25,25,0.8);
}
.container{
  width: 550px;
}
h1{
  font-size: 40px;
  font-weight: 600;
  color: white;
  font-style: normal;
  margin-top: 48px;
  margin-bottom: 10px;
}
span{
  color: white;
  font-size: 18px;
  font-weight: 400;
}
span button{
  font-size: 18px;
  font-weight: 600;
  color: rgba(191,21,21,0.4);
  outline: none;
  background: none;
  border: none;
  cursor: pointer;
  transition: 0.2s ease-out;
}
span button:hover{
  color:rgb(191, 21, 21);
}
form{
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 40px;
}
label{
  position: relative;
  height: 60px;
  margin-bottom: 10px;
}
label span{
  position: absolute;
  top: 0;
  left: 0;
  color: rgba(255, 255, 255, 0.5);
  font-size: 12px;
  font-weight: 300;
  font-style: normal;
}
input{
  background: none;
  outline: none;
  border: none;
  border-bottom: 0.3px solid rgba(255, 255, 255, 0.5);
  position: relative;
  color: rgba(255, 255, 255, 0.8);
  width: 100%;
  margin-top: 25px;
  height: 20px;
  transition: 0.2s ease-out;
}
input:hover{
  border-bottom: 0.3px solid rgba(255, 255, 255, 0.8);
}
input:focus{
    border-bottom: 0.3px solid rgba(191, 21, 21, 0.7);
}
img{
  position: absolute;
  right: 0;
  bottom: 17px;
  cursor: pointer;
}
.btn{
  background-color: rgba(191,21,21,0.4);
  border: none;
  outline: none;
  color: white;
  height: 46px;
  margin-top: 30px;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  transition: 0.1s ease-out;
  cursor: pointer;
}
.btn:hover{
    background-color: rgba(191, 21, 21, 0.6);
}
</style>
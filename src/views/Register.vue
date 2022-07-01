<template>
    <div class="holder">
        <form class="form" id="register-form" @submit.prevent="registerForm">
            <h2 class="register-text mb-4">REGISTER</h2>

            <div class="input-group my-3">
                <input type="email" class="form-control shadow-none py-3" v-model="username" placeholder="Email Address">
            </div>
            <div class="input-group my-3">
                <input type="password" class="form-control shadow-none py-3" placeholder="Password" v-model="password">
            </div>
            <div class="input-group my-3">
                <input type="password" class="form-control shadow-none py-3" placeholder="Confirm Password" v-model="password2">
            </div>
            <div class="input-group my-3">
                <input type="submit" value="Register" class="btn btn-primary" id="submitBtn" style="background-color:rgb(7, 52, 17); color:white">
            </div>
            <p class="text-center" style="font-weight: bold;">Already have an account? <router-link to="/login" style="text-decoration:none; color:white;">Login</router-link></p>

        </form>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name : 'Register',
    data(){
        return{
            email : '',
            username : '',
            password : '',
            password2 : ''
        }
    },
    methods:{
        registerForm(){
            if(this.password === this.password2){
                const formData = {
                    username : this.username,
                    email : this.username,
                    password : this.password
                }
                axios.post('/api/v1/users/', formData)
                .then(response=>{
                    this.$router.push('/login')
                    console.log(response)
                })
                .catch(error=>{
                    console.log(error)
                })
            }else{
                alert('Passwords do not match')
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.holder{
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    background-image: linear-gradient(rgb(82, 176, 104), rgb(227, 240, 231));
    height: 100vh;
}
.form{
    width: 30%;
    border-radius: 20px;
    padding: 50px 10px;
    background-color: rgb(82, 176, 104) !important;
}
.input-group{
    width: 80%;
    margin: 0 auto;
}
.register-text{
    color: white !important;
    text-align: center;
}
#submitBtn{
    margin: 0 auto;
    padding: 10px 20px;
    width: 100% !important;
}
</style>
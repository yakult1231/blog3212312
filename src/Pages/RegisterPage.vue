<template>
    <div class ="bg-gray-200 p-10 w-screen h-screen flex justify-center">
        <div class = "bg-white relative rounded-[35px] p-[10px] h-[85vh] w-[65vw]">
            <div class = "flex grid-cols-1 bg-gray-50 rounded-[25px]">
                <div class = "self-center">
                    <img src="../assets/images/Screenshot 2024-01-21 110002.png" alt="" class = "rounded-[25px] h-[82vh] w-full">
                </div>
                <h4 class=" z-10 text-xs left-3/4 top-7 absolute w-full text-gray-500 font-bold">Already a Member? <button>
                    <a class=" text-blue-400" href="/login">Login Here!</a>
                </button></h4>
                
                <div class = "relative w-7/12 flex justify-center items-center flex-col">
                    <div class="absolute top-[200px] right-[100px] opacity-15 bg-blue-300 w-[200px] h-[200px]"></div>
                    <div class="absolute top-[160px] right-[70px] backdrop-blur-md w-[260px] h-[260px]"></div>
                    <div class="absolute top-[400px] right-[160px] opacity-30 bg-red-200 w-[250px] h-[50px]"></div>
                    <div class="absolute top-[420px] right-[130px] backdrop-blur-md w-[305px] h-[50px]"></div>


                    <div class="flex justify-center items-center flex-col absolute">
                        <h1 class="text-3xl font-sans">Create your account!</h1>
                        <h2 class="mt-3">Join our 100 million Users!</h2>
                        <input v-model="username" type="text" placeholder="Enter Username" class=" rounded-md shadow-md mt-7 pl-3  pr-28 py-4">
                        <div class="relative">
                            <input v-model="password" :type="isPasswordHidden ? 'password' : 'text'"  placeholder="Password" class="rounded-md shadow-md mt-4 pl-3  pr-28 py-4">
                            <button class=" w-[50px] h-[50px] absolute top-5 right-1" @click="isPasswordHidden = !isPasswordHidden">
                                <FontAwesomeIcon class=" text-lg" :icon="`fa-solid ${isPasswordHidden ? 'fa-eye' : 'fa-eye-slash'}`" />
                            </button>
                        </div>
    
                        <div class="mt-5 mb-6 justify-between flex w-11/12" >
                            <h1></h1>
                        </div>
                        <div>
                            <button click="onRegister" class=" bg-red-400 hover:bg-red-500 delay-50 px-32 py-4 rounded-md text-white shadow-md shadow-red-400 hover:shadow-red-500">Register</button>
                        </div>
                        <h4 class=" mt-5 text-xs text-gray-500 font-bold">Or continue with</h4>
                        <div class="flex mt-4">
                            <button class="mx-4 hover:bg-white hover:shadow-2xl px-6 py-3 rounded-md"><img class="w-[2vw]" src="../assets/images/free-google-1772223-1507807.webp" alt=""></button>
                            <button class="mx-4 hover:bg-white hover:shadow-2xl px-6 py-3 rounded-md"><img class="w-[2vw]" src="../assets/images/16-apple-512.webp" alt=""></button>
                            <button class="mx-4 hover:bg-white hover:shadow-2xl px-6 py-3 rounded-md"><img class="w-[2vw]" src="../assets/images/download.png" alt=""></button>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script land="ts">
    import { defineComponent } from 'vue'
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
    import api from '../views/api'


    export default defineComponent({
        data() {
            return {
                isPasswordHidden: false,
            }
        },
        components:{
            FontAwesomeIcon,
        },
        methods:{
            onregister() {
                    console.log(this.username, this.password);
                    api
                    
                        .post('/auth/register', {
                            username: this.username,
                            password: this.password
                        })
                        .then((resp) =>{
                            localStorage.setItem('token', resp.data.token)
                        })
    
                        .catch((err) => {
                            console.error(err)
                            alert(err.message)
                        })
                }
        }
    })
</script>
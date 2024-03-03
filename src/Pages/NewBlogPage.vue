<template>
    <div class ="bg-gray-200 p-10 w-screen h-screen flex justify-center">
        <div class = "bg-white relative rounded-[35px] p-[10px] h-[85vh] w-[65vw]">
            <div class = "justify-center flex items-center flex-col bg-gray-50 rounded-[25px] h-full">
                <div class="w-6/12 justify-center flex items-center flex-col">
                    <h1 class="my-5 text-3xl font-bold">New Blog</h1>   
                    
                    <div>
                        <h2 class="my-5 text-xl font-bold">Title:</h2>
                            <input type="text" class="border-black rounded-md border-2 pr-20">
                    </div>
    
                    <div>
                        <h2 class="my-5 text-xl font-bold">Body:</h2>
                        <input type="text" class="border-black rounded-md border-2 pr-20 pb-32">
                    </div>
    
                    <button @click="onCreateblog" class="border-black delay-15 hover:bg-black hover:border-white hover:text-white mt-10 rounded-md border-2 px-10 py-2"> Save </button>
                </div>
            </div>
        </div>
    </div>
</template>
<!-- 
/*
git add -A
git commit -m “first commit”
git push -uoriginmaster
*\ -->


<script lang="ts">
    import { defineComponent } from 'vue'
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
    import api from '@/views/api';

    export default defineComponent({
        data() {
            return {
                Title: '',
                Body: '',
            }
        },
        components:{

        },

        methods: {
            onCreateblog() {
                console.log(this.Title, this.Body);
                api
                    .post('/blog/createblog', {
                        Title: this.Title,
                        Body: this.Body
                    }, 
                        {
                            headers: {
                                'Authorization': "Bearer ${token}"
                            }  
                        }  
                    )

                    
                    .then((resp:any) =>{
                        localStorage.setItem('token', resp.data.token)
                        return resp.data;
                    })

                    .catch((err:any) => {
                        console.error(err)
                        alert(err.message)
                    })
            }
        }
        
    })
</script>
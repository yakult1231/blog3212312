<template>
    <div class ="bg-gray-200 p-10 w-screen h-screen flex justify-center">
        <div class = "bg-white relative rounded-[35px] p-[10px] h-[85vh] w-[65vw]">
            <div class = "justify-center flex grid-cols-1 bg-gray-50 rounded-[25px] h-full">
                <div class ="p-32 bg-black w-1/4 h-1/4 self-center"></div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

    export default defineComponent({
        data() {
            return {
                isPasswordHidden: false,
            }
        },
        components:{
            FontAwesomeIcon,
        }
    })
</script>
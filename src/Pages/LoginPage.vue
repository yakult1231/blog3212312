<template>
    <div class ="bg-gray-200 p-10 w-screen h-screen flex justify-center">
        <div class = "bg-white  rounded-[35px] p-[10px] h-[80vh] w-[60vw]">
            <div class = "flex grid-cols-1 bg-gray-50 rounded-[25px]">
                <div class = "self-center">
                    <img src="../assets/images/Screenshot 2024-01-21 110002.png" alt="" class = "rounded-[25px] h-[77vh] w-full">
                </div>
    
                <div class = " w-7/12 flex justify-center items-center flex-col">
                        <h4 class="mt-10 text-xs absolute top-10 right-27 text-gray-500 font-bold">Not a member? <a class=" text-blue-400" href="">Register Now!</a></h4>
                        <h1 class="text-3xl font-sans">Hello Again!</h1>
                        <h2 class="mt-3">Welcome back, you've been missed!</h2>
                        <input type="text" placeholder="Enter Username" class=" rounded-md shadow-md mt-7 pl-3  pr-28 py-4">
                        <input type="text" placeholder="Password" class="rounded-md shadow-md mt-4 pl-3  pr-28 py-4">
                        <div class="mt-5 mb-6 justify-between flex w-7/12">
                            <h1></h1>
                            <button class=" text-gray-500 text-sm j">Recovery Password</button>
                        </div>
                        <div>
                            <button class=" bg-red-400 px-32 py-4 rounded-md text-white">Sign in</button>
                        </div>
                        <h4 class=" mt-10 text-xs text-gray-500 font-bold">Or continue with</h4>
                </div>
            </div>
        </div>
    </div>
</template>
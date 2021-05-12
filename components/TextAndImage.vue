<template>
    <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-16">
        <div class="img col-span-7 pr-16">
            <div class="relative">
                <div class="w-3/5 ml-auto relative z-10 mb-10">
                    <img src="~/static/DSC_6102pp.jpg" >
                </div>
                <div class="w-3/5 mr-auto absolute -bottom-16">
                    <img src="~/static/DSC_6102pp.jpg" >
                </div>
            </div>
        </div>
        <div class="text col-span-5">
            <div class="pl-6">
                <h2 class="text-2xl font-bold my-8">Lorem ipsum dolor sit amet consectetur adipisicing elit.</h2>
                <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
                <NuxtLink to="/" class="[ inline-flex px-10 py-3 bg-blue-500 text-white font-medium border border-transparent border-solid rounded-sm hover:bg-black transition-all ] btn__main">
                            Więcej
                </NuxtLink>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
// .btn {
//     font-size: 16px;
//     font-weight: 400;
//     line-height: 50px;
//     display: inline-flex;
//     align-items: center;
//     justify-content: center;
//     height: 52px;
//     padding: 0 40px;
//     cursor: pointer;
//     white-space: nowrap;
//     border: 1px solid transparent;
//     border-radius: 2px;
//     outline: none;

//     &__main {
//         border-color: #1292ee;
//         background-color: #1292ee;
//         color: #fff;
//     }

// }


</style>

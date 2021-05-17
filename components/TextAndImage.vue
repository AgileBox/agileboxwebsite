<template>
    <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-16">
        <div class="img col-span-7 pr-16">
            <div class="relative">
                <div class="w-3/5 ml-auto relative z-10 mb-10 shadow-2xl">
                    <img src="~/static/DSC_6102pp.jpg" class="rounded-lg">
                </div>
                <div class="w-3/5 mr-auto absolute -bottom-16 shadow-lg">
                    <img src="~/static/DSC_6102pp.jpg" class="rounded-lg">
                </div>
            </div>
        </div>
        <div class="text col-span-5">
            <div class="pl-6">
                <h2 class="text-2xl font-bold my-8">Lorem ipsum dolor sit amet consectetur adipisicing elit.</h2>
                <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
                <Btn />
            </div>
        </div>
    </div>
</template>

<script>

import Btn from '~/components/Btn.vue'

export default {
    components: {
        Btn
    },

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

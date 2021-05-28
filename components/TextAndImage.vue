<template>
    <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-4 md:mb-16">
        <div class="img col-span-12 md:col-span-7 mb-6 md:mb-0 md:pr-16">
            <div class="relative">
                <div class="w-3/5 ml-auto relative z-10 mb-10 shadow-2xl">
                    <img :src="image1" class="rounded-lg">
                </div>
                <div class="w-3/5 mr-auto absolute -bottom-16 shadow-lg">
                    <img :src="image2" class="rounded-lg">
                </div>
            </div>
        </div>
        <div class="text col-span-12 md:col-span-5">
            <div class="pl-6">
                <h2
                    v-if="heading"
                    class="text-2xl font-bold my-8"
                >
                    {{ heading }}
                </h2>
                <slot />
            </div>
        </div>
    </div>
</template>

<script>


export default {
    props: {
        heading: String,
        image1: String,
        image2: String
    },
}
</script>

<style lang="scss">

</style>

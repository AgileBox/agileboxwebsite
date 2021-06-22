<template>
    <div class="banner h-96 sm:h-screen relative text-white">
        <img src="~/static/banner-main.jpg" class="h-full w-full object-cover object-top absolute">
        <div class="wrapper h-full relative z-10 flex items-center">
            <div class="grid grid-cols-5">
                <h1
                    v-html="slogan"
                    class="text-2xl sm:text-4xl lg:text-6xl col-span-3 lg:col-span-3 font-extrabold"
                ></h1>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        slogan: String
    }
}
</script>

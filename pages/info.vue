<template>
    <section class="aboutUs">
        <BannerSubpage />
        <TextAndImage
            :image1="require('~/static/DSC_6102pp.jpg')"
            :image2="require('~/static/DSC_6102pp.jpg')"
            heading="Lorem ipsum dolor sit amet consectetur adipisicing elit."
        >
            <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
        </TextAndImage>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-6">
                <div class="col-span-5">
                    <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2>
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Luizie</h1>
                        <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
                </div>
                <div class="img col-span-7 pl-16">
                    <img src="~/static/DSC_6102pp.jpg" class="shadow-2xl rounded-lg">
                </div>
            </div>
        </div>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-6 mb-16">
                <div class="img col-span-7 pr-16">
                    <img src="~/static/DSC_6102pp.jpg" class="shadow-2xl rounded-lg">
                </div>
                <div class="col-span-5">
                    <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2>
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Dorocie</h1>
                        <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import TextAndImage from '~/components/TextAndImage.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        TextAndImage
    },
}
</script>

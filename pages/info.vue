<template>
    <section class="aboutUs">
        <BannerSubpage
            title="O nas"
            :image="require('~/static/DSC_6238pp 2.jpg')"
            :breadcrumb-items="[
                {name: 'Home', href: '/'},
                {name: 'O nas'}
            ]"
        />
        <HeaderAndText
            class="text-center"
            :title="content.title"
        >
        </HeaderAndText>
        <TextAndImage
            :image1="require('~/static/DSC_6322pp.jpg')"
            :image2="require('~/static/DSC_6254pp.jpg')"
        >
            <h3
                v-html="content.subtitle"
                class="text-gray-500 text-xl font-bold my-4"
            >
            </h3>
            <p
                v-html="content.text"
                class="text-gray-500"
            >
            </p>
        </TextAndImage>
        <HeaderAndText
            class="text-center"
            subtitle="Gdybyśmy miały przedstawić nasze wspólne doświadczenie w liczbach, to byłoby to w sumie:"
            is-wide
        >
            <ul class="grid grid-cols-12 mt-6 md:mt-0">
                <li
                    v-for="(item, index) in content.numbers"
                    :key="index"
                    class="col-span-12 sm:col-span-6 md:col-span-3 p-4"
                >
                    <p class="text-4xl font-bold text-blue-500 mb-2">{{ item.number }}</p>
                    <p class="text-gray-500 font-bold mb-2">{{ item.description }}</p>
                    <p class="text-gray-500 text-sm">{{ item.more }}</p>
                </li>
            </ul>
        </HeaderAndText>
        <HeaderAndText
            class="text-left md:text-center"
            :subtitle="content.summary"
        >
        </HeaderAndText>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-6">
                <div class="col-span-12 md:col-span-5">
                    <!-- <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2> -->
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Luiza Lipień</h1>
                    <p
                        v-html="content.luiza"
                        class="text-gray-500 mb-8"
                    >
                    </p>
                </div>
                <div class="img col-span-12 md:col-span-7 md:pl-16">
                    <img src="~/static/DSC_6137pp.jpg" class="shadow-2xl rounded-lg">
                </div>
            </div>
        </div>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-6 mb-16">
                <div class="img col-span-12 md:col-span-7 md:pr-16 mb-6 md:mb-0">
                    <img src="~/static/DSC_6423pp2.jpg" class="shadow-2xl rounded-lg">
                </div>
                <div class="col-span-12 md:col-span-5">
                    <!-- <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2> -->
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Dorota Sternalska</h1>
                    <p
                        v-html="content.dorota"
                        class="text-gray-500 mb-8"
                    >
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import TextAndImage from '~/components/TextAndImage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        TextAndImage,
        HeaderAndText
    },

    async asyncData() {
        const content = await import('~/content/data/info.json')

        return {
            content
        }
    }
}
</script>

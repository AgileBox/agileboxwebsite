<template>
    <div class="wrapper mb-16">
        <swiper class="swiper" :options="swiperOption" ref="swiper">
            <swiper-slide
                v-for="(item, index) in quotes"
                :key="index"
                class="mb-6"
            >
                <Card class="text-center mb-6">
                    <div class="font-serif text-9xl text-blue-500 -mb-14">
                        &rdquo;
                    </div>
                    <p class=" text-gray-500 mb-4">
                        {{ item.text }}
                    </p>
                    <p class="text-blue-500 uppercase mb-1">
                        {{ item.name }}
                    </p>
                    <p class="text-gray-500 text-sm">
                        {{ item.function }}
                    </p>
                </Card>
            </swiper-slide>

            <div slot="pagination" class="swiper-pagination"></div>
        </swiper>
    </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import Card from '~/components/Card.vue'
import 'swiper/css/swiper.css'

export default {
    components: {
        Card,
        Swiper,
        SwiperSlide
    },
    directives: {
        swiper: directive
    },
    props: {
        quotes: String
    },

    data: () => ({
        swiperOption: {
            slidesPerView: 1,
            spaceBetween: 10,
            breakpoints: {
                768: {
                    slidesPerView: 3,
                    slidesPerGroup: 3,
                    spaceBetween: 30,
                },
            },
            pagination: {
                el: '.swiper-pagination',
                clickable: true
            }
        },
    })
}
</script>

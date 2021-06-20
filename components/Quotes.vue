<template>
    <div class="wrapper mb-16">
        <swiper class="swiper" :options="swiperOption" ref="swiper">
            <swiper-slide
                v-for="(item, index) in quotesContent"
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

    data: () => ({
        swiperOption: {
            slidesPerView: 3,
            slidesPerGroup: 3,
            spaceBetween: 30,
            pagination: {
                el: '.swiper-pagination',
                clickable: true
            }
        },
        quotesContent: [
            {
                text: "Luiza has been a terrific coach and mentor for my team. She lives the agile principles and is completely outcome focused. What impresses me about Luiza is that she works from the bottom up and focuses on all aspects of coaching.",
                name: "Suavek",
                function: "CTO"
            },
            {
                text: "Dorota is an expert in agile methodologies and software testing with both huge knowledge and experience with working in various environments, different teams and nationalities. As a result of this combination and great mentoring skills, teams led by Dorota are growing, learning and performing.",
                name: "Konrad",
                function: "Senior Software Engineer"
            },
            {
                text: "Warsztat skłonił mnie do myślenia. Już wyciagnęłam pewne wnioski, mam pomysł co chce przemyśleć, nad czym pracować. Ogromne wow - dawno nie byłam na tak ciekawym i skłaniającym do myślenia warsztacie. Dziekuję dziewczyny!",
                name: "Uczestniczka warsztatów"
            },
            {
                text: "Dorota has a lot of influence on the way of working on the entire project. What is unique, she knows and thinks how to apply some good practices in the reality/context of a particular business.",
                name: "Wojtek",
                function: "Engineering Manager"
            },
            {
                text: "I'd like to thank Luiza for helping me keep in mind that people are the biggest asset of the company and that success is dependent on how we involve people on that mission.",
                name: "Andrzej",
                function: "Director of Engineering"
            },
            {
                text: "Dorota is always actively looking for areas of improvement and has a ready toolkit with suitable techniques to hand. She built strong business relationships with the team members and is able to get them to adopt new approaches. I saw a measurable difference in the teams she coached.",
                name: "Sharon",
                function: "Programme Manager"
            },
        ]
    }),

    mounted () {
        console.log(this.$refs.swiper);
    }
}
</script>

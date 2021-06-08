<template>
    <div class="wrapper mb-16">
        <ul class="grid grid-cols-12 md:gap-8">
            <li
                v-for="(item, index) in quotesContent"
                :key="index"
                class="col-span-12 md:col-span-4"
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
            </li>
        </ul>
    </div>
</template>

<script>
import Card from '~/components/Card.vue'

export default {
    components: {
        Card
    },

    data: () => ({
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
        ]
    })
}
</script>

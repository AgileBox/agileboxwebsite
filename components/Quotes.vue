<template>
    <div class="wrapper mb-16">
        <ul class="grid grid-cols-12 gap-8">
            <li
                v-for="(item, index) in quotesContent"
                :key="index"
                class="col-span-12 md:col-span-4"
            >
                <Card class="text-center">
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
                text: "Dorota is an expert in agile methodologies and software testing with both huge knowledge and experience with working in various environments, different teams and nationalities. As a result of this combination and great mentoring skills, teams led by Dorota are growing, learning and performing.",
                name: "Konrad",
                function: "Senior Software Engineer"
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
    })
}
</script>

<style lang="scss">


</style>

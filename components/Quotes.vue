<template>
    <div class="wrapper mb-16">
        <ul class="grid grid-cols-12 gap-8">
            <li
                v-for="(item, index) in quotesContent"
                :key="index"
                class="col-span-4 p-10 border border-gray-100 rounded-lg shadow-lg text-center text-lg font-medium"
            >
                <div class="font-serif text-9xl text-blue-500 -mb-14">
                    &rdquo;
                </div>
                <p class=" text-gray-500 mb-4">
                    {{ item.text }}
                </p>
                <p class="text-blue-500  uppercase mb-4">
                    {{ item.name }}
                </p>
                <p class="text-gray-500 mb-4">
                    {{ item.function }}
                </p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data: () => ({
        quotesContent: [
            {
                text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam laborum harum rerum. Architecto aperiam perspiciatis at alias autem quo ab corporis iusto, sit saepe labore fugiat debitis odio quis voluptates!",
                name: "Jan Kowalski",
                function: "CEO"
            },
            {
                text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam laborum harum rerum. Architecto aperiam perspiciatis at alias autem quo ab corporis iusto",
                name: "Jan Kowalski",
                function: "CEO"
            },
            {
                text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam laborum harum rerum. Architecto aperiam perspiciatis at alias autem quo ab corporis iusto, sit saepe labore fugiat debitis odio quis voluptates!",
                name: "Jan Kowalski",
                function: "CEO"
            },
        ]
    })
}
</script>

<style lang="scss">


</style>

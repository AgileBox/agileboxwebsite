<template>
    <section>
        <div class="wrapper grid grid-cols-6 place-items-center mt-16 mb-16">
            <div class="text col-start-2 col-span-4">
                <div class="">
                    <h2
                        v-if="title"
                        class="text-center text-4xl font-bold my-6"
                    >
                        {{ title }}
                    </h2>
                    <h3
                        v-if="subtitle"
                        class="text-center text-xl text-gray-500 font-bold my-4"
                    >
                        {{ subtitle }}
                    </h3>
                    <slot />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        title: String,
        subtitle: String,
    },
}
</script>

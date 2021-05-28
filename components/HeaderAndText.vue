<template>
    <section
        :class="{
            'bg-gray-800 text-white py-10': isDark,
            'my-16': !isDark
        }"
        class="relative"
    >
        <div class="wrapper grid grid-cols-6 relative z-10 place-items-center">
            <div class="text col-span-6 sm:col-start-2 sm:col-span-4">
                <h2
                    v-if="title"
                    class="text-center text-4xl font-bold my-6"
                >
                    {{ title }}
                </h2>
                <h3
                    v-if="subtitle"
                    :class="isDark ? 'text-white opacity-70' : 'text-gray-500'"
                    class="text-center text-xl font-bold my-4"
                >
                    {{ subtitle }}
                </h3>
                <slot />
            </div>
        </div>
        <div
            v-if="bgImage"
            class="absolute top-0 left-0 h-full w-full">
            <img :src="bgImage" class="h-full w-full object-cover object-top opacity-10">
        </div>
    </section>
</template>

<script>
export default {
    props: {
        title: String,
        subtitle: String,
        isDark: Boolean,
        bgImage: String
    },
}
</script>

<template>
    <div
        :class="{
            'banner-subpage--has-img': image
        }"
        class="banner-subpage relative bg-gray-800 text-white"
        >
        <img
            v-if="image"
            :src="image"
            class="h-full w-full object-cover object-top absolute opacity-50"
        >
        <div class="wrapper h-full relative z-10 flex justify-center items-center">
            <div class="text-center pt-20">
                <h1 class="text-2xl sm:text-4xl font-bold mb-2">
                    {{ title }}
                </h1>
                <Breadcrumbs
                    v-if="breadcrumbItems && breadcrumbItems.length"
                    :items="breadcrumbItems"
                    class="inline-block"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Breadcrumbs from '~/components/Breadcrumbs.vue'

export default {
    components: {
        Breadcrumbs
    },

    props: {
        title: String,
        image: String,
        breadcrumbItems: Array
    }
}
</script>

<style lang="scss">
.banner-subpage {
    height: 30vh;
    min-height: 250px;

    &--has-img {
        height: 50vh;
        min-height: 300px;
    }
}

</style>

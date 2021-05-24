<template>
    <div class="banner-subpage relative bg-gray-800 text-white">
        <img src="~/static/DSC_6409pp3.jpg" class="h-full w-full object-cover object-top absolute opacity-20">
        <div class="wrapper h-full relative z-10 flex justify-center items-center">
            <div class="grid grid-cols-6">
                <div class="text-center col-start-2 col-span-4">
                    <h1 class="text-4xl font-bold mb-6">
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
        breadcrumbItems: Array
    }
}
</script>

<style lang="scss">
.banner-subpage {
    height: 50vh;
    min-height: 400px;
}

</style>

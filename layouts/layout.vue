<template>
    <section class="layout">
        <Header :is-scrolled="isScrolled" />
        <div class="content">
            <nuxt />
        </div>
        <footer class="bg-gray-800 text-white text-xs sm:text-base py-10">
            <div class="wrapper flex justify-between items-center">
                <div class="">
                    &copy; AgileBox
                </div>
                <NuxtLink to="/privacy" class="">
                    Polityka Prywatności
                </NuxtLink>
                <div class="">
                    Wykonanie:<br>Notka Ewa Perończyk
                </div>
            </div>
        </footer>
        <a
            v-if="isScrolled"
            class="fixed flex items-center justify-center right-8 bottom-20 bg-blue-500 border border-transparent w-10 h-10 lg:w-14 lg:h-14 rounded-full z-99 cursor-pointer"
            @click.prevent="scrollTop"
        >
            <Icon glyph="arrow-up" class="text-base lg:text-xl text-white" />
        </a>
    </section>
</template>

<script>
import Header from '~/components/Header.vue'
import Icon from '~/components/Icon.vue'

export default {
    name: 'Layout',

    components: {
        Header,
        Icon
    },

    data: () => ({
        isScrolled: false
    }),

    methods: {
        scrollTop() {
            window.scrollTo({top: 0, behavior: 'smooth'});
        }
    },

    mounted() {
        window.addEventListener('scroll', () => {
            this.isScrolled = document.documentElement.scrollTop !== 0;
        })
    },
}
</script>

<style lang="scss">
.wrapper {
    padding: 0 40px;

    @media (min-width: 1340px) {
        max-width: 1280px;
        margin-left: auto;
        margin-right: auto;
    }
}
</style>

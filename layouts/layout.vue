<template>
    <section class="layout flex flex-col">
        <Header :is-scrolled="isScrolled" />

        <div class="content pb-10">
            <nuxt />
        </div>

        <footer class="mt-auto bg-gray-800 text-white text-xs sm:text-base py-10">
            <div class="wrapper flex justify-between items-center opacity-60 text-xs">
                <div>
                    &copy; AgileBox
                </div>
                <NuxtLink to="/privacy">
                    Polityka Prywatności
                </NuxtLink>
                <div>
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

    head() {
        return {
            link: [
                { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Mulish:ital,wght@0,400;0,500;0,700;0,800;1,400;1,500;1,700;1,800&display=swap' },
                { rel: 'stylesheet', href: 'https://cdn.linearicons.com/free/1.0.0/icon-font.min.css' }
            ]
        }
    },

    components: {
        Header,
        Icon
    },

    data: () => ({
        isScrolled: false
    }),

    mounted() {
        window.addEventListener('scroll', () => {
            this.isScrolled = document.documentElement.scrollTop !== 0;
        })
    },

    methods: {
        scrollTop() {
            window.scrollTo({top: 0, behavior: 'smooth'});
        }
    },
}
</script>

<style lang="scss">
.wrapper {
    padding: 0 24px;

    @media (min-width: 960px) {
        padding: 0 40px;
    }

    @media (min-width: 1340px) {
        max-width: 1280px;
        margin-left: auto;
        margin-right: auto;
    }

}
</style>

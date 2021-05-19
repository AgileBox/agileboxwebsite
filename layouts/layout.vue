<template>
    <section class="layout">
        <Header />
        <div class="content">
            <nuxt />
        </div>
        <footer class="bg-gray-800 text-white py-10">
            <div class="wrapper flex justify-between items-center">
                <div class="">
                    &copy; AgileBox
                </div>
                <div class="">
                    Polityka Prywatności
                </div>
                <div class="">
                    Wykonanie:<br>Notka Ewa Perończyk
                </div>
            </div>
        </footer>
    </section>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
    name: 'Layout',

    components: {
        Header
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

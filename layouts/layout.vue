<template>
    <section class="layout">
        <Header :is-info-page="isInfoPage" />
        <div class="content">
            <nuxt />
        </div>
    </section>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
    name: 'Layout',

    components: {
        Header
    },

    computed: {
        isInfoPage() {
            return this.$nuxt._route.name === "info" && true
        }
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

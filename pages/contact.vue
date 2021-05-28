<template>
    <section class="contact">
        <BannerSubpage
            title="Kontakt"
            :image="require('~/static/DSC_6102pp.jpg')"
            :breadcrumb-items="[
                {name: 'Home', href: '/'},
                {name: 'Kontakt'}
            ]"
        />
        <ContactSection class="mt-6" />
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import ContactSection from '~/components/ContactSection.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        ContactSection
    },
}
</script>

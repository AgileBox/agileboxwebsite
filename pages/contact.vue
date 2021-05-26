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
        <HeaderAndText
            title="Kontakt"
            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit quas, maiores debitis ut beatae quibusdam."
        />
        <Quotes />
        <ContactSection />
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'
import ContactSection from '~/components/ContactSection.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        HeaderAndText,
        ContactSection
    },
}
</script>

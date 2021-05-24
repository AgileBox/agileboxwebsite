<template>
    <section class="offer">
        <BannerSubpage
            title="Oferta"
            :breadcrumb-items="[
                {name: 'Home', href: '/'},
                {name: 'Oferta'}
            ]"
        />
        <HeaderAndText
            class="text-center"
            title="Co robimy"
            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
        >
            <p class="text-gray-500 mb-6">
                Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio vel asperiores qui nemo quaerat et laboriosam quos dolore. Dignissimos rerum dolore optio hic laudantium odit molestiae mollitia doloremque. Sunt, laudantium.
            </p>
        </HeaderAndText>
        <HeaderAndText
            title="Rekomendacje"
            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit quas, maiores debitis ut beatae quibusdam."
        />
        <Quotes />
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'
import Quotes from '~/components/Quotes.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        HeaderAndText,
        Quotes
    },
}
</script>

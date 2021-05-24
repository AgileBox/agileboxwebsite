<template>
    <section class="privacy">
        <BannerSubpage
            title="Polityka prywatności"
            :breadcrumb-items="[
                    {name: 'Home', href: '/'},
                    {name: 'Polityka prywatności'}
                ]"
        />
        <HeaderAndText
            title="Polityka prywatności"
        >
            <p class="text-gray-500 mb-6">
                Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia.
            </p>
        </HeaderAndText>
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        HeaderAndText
    },
}
</script>

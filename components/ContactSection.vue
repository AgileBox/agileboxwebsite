<template>
    <div class="wrapper grid grid-cols-12 gap-8 mb-16">
            <Card class="col-span-12 md:col-span-4">
                <div class="flex items-center xl:items-start flex-col xl:flex-row">
                    <Icon glyph="laptop-phone" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                    <div>
                        <h4 class="mb-4">Adres</h4>
                        <p class="text-gray-500">ul Jakastam<br>Kraków</p>
                    </div>
                </div>
            </Card>
            <Card class="col-span-12 md:col-span-4">
                <div class="flex items-center xl:items-start flex-col xl:flex-row">
                    <Icon glyph="phone-handset" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                    <div>
                        <h4 class="mb-4">Telefon</h4>
                        <p class="text-gray-500">333 654 678<br>666 888 999</p>
                    </div>
                </div>
            </Card>
            <Card class="col-span-12 md:col-span-4">
                <div class="flex items-center xl:items-start flex-col xl:flex-row">
                    <Icon glyph="laptop" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                    <div>
                        <h4 class="mb-4">E-mail</h4>
                        <p class="text-gray-500">kontakt@agilebox.pl</p>
                    </div>
                </div>
            </Card>
        </div>
</template>

<script>

import Card from '~/components/Card.vue'
import Icon from '~/components/Icon.vue'

export default {

    components: {
        Card,
        Icon
    },
}
</script>

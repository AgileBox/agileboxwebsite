<template>
    <div class="wrapper grid grid-cols-12 gap-8 mb-16">
        <Card class="col-span-12 md:col-span-4">
            <div class="flex items-center xl:items-start flex-col xl:flex-row">
                <Icon glyph="users" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                <div>
                    <h4 class="mb-4">Facebook</h4>
                    <a href="https://www.facebook.com/Akademia-Scrum-Mastera-112618523807367" target="_blank" class="text-gray-500">Akademia Scrum Mastera</a>
                </div>
            </div>
        </Card>
        <Card class="col-span-12 md:col-span-4">
            <div class="flex items-center xl:items-start flex-col xl:flex-row">
                <Icon glyph="envelope" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                <div>
                    <h4 class="mb-4">E-mail</h4>
                    <p class="text-gray-500">kontakt@agilebox.pl</p>
                </div>
            </div>
        </Card>
        <Card class="col-span-12 md:col-span-4">
            <div class="flex items-center xl:items-start flex-col xl:flex-row">
                <Icon glyph="license" class="text-5xl text-blue-500 mr-8 mb-4 xl:mb-0" />
                <div>
                    <h4 class="mb-4">Linkedin</h4>
                    <a href="https://pl.linkedin.com/in/dorota-sternalska" target="_blank" class="text-gray-500">Dorota Sternalska</a><br>
                    <a href="https://www.linkedin.com/in/luiza-lipień/" target="_blank" class="text-gray-500">Luiza Lipień</a>
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

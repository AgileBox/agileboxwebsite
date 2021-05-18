<template>
    <form class="my-10">
        <input class="px-10 py-3 -mr-1 border border-transparent border-solid rounded-l-sm" type="email" placeholder="Podaj swój e-mail">
        <Btn>Zapisz się</Btn>
    </form>
</template>

<script>

import Btn from '~/components/Btn.vue'

export default {
    components: {
        Btn
    },
}
</script>

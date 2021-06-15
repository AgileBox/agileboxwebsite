<template>

    <a :href="href" class="inline-flex px-6 sm:px-10 py-2 sm:py-3 bg-blue-500 text-white font-medium border border-transparent border-solid rounded-sm hover:bg-black transition-all">
        <slot>Więcej</slot>
    </a>

</template>

<script>
export default {
    props: {
        href: String
    }
}
</script>

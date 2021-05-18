<template>

    <span :class="`lnr lnr-${glyph}`"></span>

</template>

<script>
export default {
    props: {
        glyph: String
    }
}
</script>

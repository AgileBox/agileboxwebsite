<template>
    <div>
        <Banner />
        <TextAndImage />
    </div>
</template>

<script>
import Banner from '~/components/Banner.vue'
import TextAndImage from '~/components/TextAndImage.vue'

export default {
    layout: 'layout',

    components: {
        Banner,
        TextAndImage
    },

    // async asyncData() {
    //     // create context via webpack to map over all blog posts
    //     const allPosts = await require.context("~/content/blog-posts/", true, /\.md$/)
    //     const posts = allPosts.keys().map((key) => {
    //         // give back the value of each post context
    //         return allPosts(key)
    //     });
    //     return {
    //         posts
    //     }

}
</script>

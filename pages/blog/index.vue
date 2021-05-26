<template>
    <div>
        <BannerSubpage
            title="Blog"
            :image="require('~/static/DSC_6449pp.jpg')"
            :breadcrumb-items="[
                {name: 'Home', href: '/'},
                {name: 'Blog'}
            ]"
        />
        <BlogList :posts="posts" />
    </div>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import BlogList from '~/components/BlogList.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        BlogList
    },

    async asyncData() {
        // create context via webpack to map over all blog posts
        const allPosts = await require.context("~/content/blog-posts/", true, /\.md$/)
        const posts = allPosts.keys().map((key) => {
            // give back the value of each post context
            return allPosts(key)
        });
        return {
            posts
        }
    }
}
</script>

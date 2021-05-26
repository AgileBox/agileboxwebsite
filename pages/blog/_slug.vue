<template>
    <article class="blog">
        <BannerSubpage
            title="Blog"
            :breadcrumb-items="[
                    {name: 'Home', href: '/'},
                    {name: 'Blog'}
                ]"
        />
        <figure class="blog__hero">
            <!-- <img :src="post.attributes.hero_image" :alt="post.attributes.title"> -->
        </figure>

        <div class="blog__info" >
            <!-- <h1>{{ post.attributes.title }}</h1> -->
            <h3>{{ formattedDate }}</h3>
        </div>

        <!-- <div v-html="post.html" class="blog__body"></div> -->

        <div class="blog__footer">
            <!-- <h2>Written By: {{ post.attributes.author }}</h2> -->
            <NuxtLink :to="`/blog/${nextBlogPath}`">
                &gt;
            </NuxtLink>
        </div>
    </article>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage
    },

    computed: {
        formattedDate() {
            // return new Date(this.post.attributes.date).toDateString().slice(4)
            return ""
        },
        nextBlogPath() {
            // const firstBlogPath = this.sortedPaths[0]
            // // if there's no 'next' path, return the first path
            // const nextPath = isNull(this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) + 1]) ? firstBlogPath : this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) + 1]
            // function isNull(item) {
            //     return item === null || item === undefined
            // }
            // return nextPath
            return ""
        }
    },

    // get the slug as a param to import the correct md file
    async asyncData({ params }) {
        try {
            const sortedPaths = "";
            const currentPath = "";
            const post = await import(`~/content/blog-posts/${params.slug}.md`);
            console.log(params, post);
            // const currentPath = params.slug
            // // get current post data
            // // get all post data for next route
            // const allPosts = await require.context("~/content/blog-posts/", true, /\.md$/)
            // const posts = allPosts.keys().map((key) => {
            //     return allPosts(key)
            // });
            // const sortedPosts = posts.sort((a,b) => {
            //     const dateA = new Date(a.attributes.date);
            //     const dateB = new Date(b.attributes.date);
            //     if (dateA < dateB) {
            //         return 1;
            //     }
            //     if (dateA > dateB) {
            //         return -1;
            //     }
            //     return 0;
            // })
            // const sortedPaths = []
            // sortedPosts.map(post => {
            //     // clean up the path - split by /
            //     let relPath = post.attributes._meta.resourcePath.split('/')
            //     // get the end of the path, remove '.md'
            //     relPath = relPath[relPath.length - 1].slice(0, -3)
            //     sortedPaths.push(relPath)
            // })
            return {
                sortedPaths,
                post,
                currentPath
            }
        } catch(err) {
            return false
        }
    },
}
</script>

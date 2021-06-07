<template>
    <article>
        <template v-if="post">
            <BannerSubpage
                :title="post.attributes.title"
                :breadcrumb-items="[
                    {name: 'Home', href: '/'},
                    {name: 'Blog', href: '/blog'},
                    {name: 'Wpis'}
                ]"
            />
            <div class="wrapper grid grid-cols-12 place-items-center mt-4 mb-16">
                <div class="md:col-start-3 md:col-span-8 col-span-12">
                    <div class="text-gray-400 text-sm py-6">
                        <h3>{{ formatDate(post.attributes.date) }}</h3>
                    </div>
                    <div class="mb-10 shadow-2xl">
                        <img :src="post.attributes.hero_image" class="rounded-lg">
                    </div>

                    <div v-html="post.html" class="article"></div>

                    <!-- <div v-if="nextBlogPath">
                        <NuxtLink :to="`/blog/${nextBlogPath}`">
                            Next &gt;
                        </NuxtLink>
                    </div> -->
                </div>
            </div>
        </template>

        <div v-else>
            <h1>404</h1>
            <h2>Blog post not found</h2>
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
            return (this.post)
                ? new Date(this.post.attributes.date).toDateString().slice(4)
                : ''
        },
        nextBlogPath() {
            const firstBlogPath = this.sortedPaths[0]
            // if there's no 'next' path, return the first path
            const nextPath = isNull(this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) + 1]) ? firstBlogPath : this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) + 1]
            function isNull(item) {
                return item === null || item === undefined
            }
            return nextPath
        }
    },

    // get the slug as a param to import the correct md file
    async asyncData({ params }) {
        try {
            const currentPath = params.slug
            const post = await import(`~/content/blog-posts/${currentPath}.md`);

            // get current post data
            // get all post data for next route
            const allPosts = await require.context("~/content/blog-posts/", true, /\.md$/)
            const posts = allPosts.keys().map((key) => {
                return allPosts(key)
            });
            const sortedPosts = posts.sort((a,b) => {
                const dateA = new Date(a.attributes.date);
                const dateB = new Date(b.attributes.date);
                if (dateA < dateB) {
                    return 1;
                }
                if (dateA > dateB) {
                    return -1;
                }
                return 0;
            })
            const sortedPaths = []
            sortedPosts.map(post => {
                // clean up the path - split by /
                let relPath = post.attributes._meta.resourcePath.split('/')
                // get the end of the path, remove '.md'
                relPath = relPath[relPath.length - 1].slice(0, -3)
                sortedPaths.push(relPath)
            })
            return {
                post,
                sortedPaths,
                currentPath
            }
        } catch(err) {
            return false
        }
    },
    methods: {
        padTwo(num) {
            return String(num).padStart(2, '0');
        },
        formatDate(date) {
            const dateObj = new Date(date)
            return `${dateObj.getFullYear()}-${this.padTwo(dateObj.getMonth())}-${this.padTwo(dateObj.getDate())}`
        },
    }
}
</script>

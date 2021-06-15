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

                    <hr class="mt-10">

                    <div class="flex flex-row mt-10">
                        <div
                            v-if="prevBlogPath"
                            class=""
                        >
                            <Btn :href="`/blog/${prevBlogPath}`" class="items-center">
                                <Icon glyph="arrow-left" class="text-base lg:text-xl text-white pr-2 " /> Poprzedni
                            </Btn>
                        </div>
                        <div
                            v-if="nextBlogPath"
                            class="ml-auto"
                        >
                            <Btn :href="`/blog/${nextBlogPath}`" class="items-center">
                                Następny <Icon glyph="arrow-right" class="text-base lg:text-xl text-white pl-2 " />
                            </Btn>
                        </div>
                    </div>
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
import Btn from '~/components/Btn.vue'
import Icon from '~/components/Icon.vue'

export default {
    name: 'BlogPost',

    layout: 'layout',

    components: {
        BannerSubpage,
        Btn,
        Icon
    },
    computed: {
        prevBlogPath() {
            const nextBlogPath = this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) - 1]

            if (nextBlogPath) {
                return nextBlogPath
            }

            return null
        },

        nextBlogPath() {
            const nextBlogPath = this.sortedPaths[this.sortedPaths.indexOf(this.currentPath) + 1]

            if (nextBlogPath) {
                return nextBlogPath
            }

            return null
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

            const sortedPosts = posts.sort((a, b) => {
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

            const sortedPaths = sortedPosts.map(({ attributes }) => attributes.slug)

            return {
                posts,
                sortedPosts,
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

<template>
    <div>
        <Banner />
        <TextAndImage />
        <BlogList :posts="posts" />
        <div class="bg-gray-50 pb-6">
            <HeaderAndText
                title="Co robimy"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
            >
                <p class="text-center text-gray-500 mb-4">
                    Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia.
                </p>
                <NuxtLink to="/" class="[ inline-flex px-10 py-3 bg-blue-500 text-white font-medium border border-transparent border-solid rounded-sm hover:bg-black transition-all ] btn__main">
                            Więcej
                </NuxtLink>
            </HeaderAndText>
            <HeaderAndText
                title="Rekomendacje"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit quas, maiores debitis ut beatae quibusdam."
            >
            </HeaderAndText>
            <Quotes />
        </div>
    </div>
</template>

<script>
import Banner from '~/components/Banner.vue'
import TextAndImage from '~/components/TextAndImage.vue'
import BlogList from '~/components/BlogList.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'
import Quotes from '~/components/Quotes.vue'

export default {
    layout: 'layout',

    components: {
        Banner,
        TextAndImage,
        BlogList,
        HeaderAndText,
        Quotes
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

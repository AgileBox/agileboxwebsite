<template>
    <div>
        <Banner />
        <TextAndImage />
        <BlogList :posts="posts" />
        <div class="bg-gray-50">
            <HeaderAndText
                title="Co robimy"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
            >
                <p class="text-center text-gray-500 mb-4">
                    Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia.
                </p>
            </HeaderAndText>
            <HeaderAndText
                title="Rekomendacje"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit quas, maiores debitis ut beatae quibusdam."
            >
            </HeaderAndText>
        </div>
    </div>
</template>

<script>
import Banner from '~/components/Banner.vue'
import TextAndImage from '~/components/TextAndImage.vue'
import BlogList from '~/components/BlogList.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'

export default {
    layout: 'layout',

    components: {
        Banner,
        TextAndImage,
        BlogList,
        HeaderAndText
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

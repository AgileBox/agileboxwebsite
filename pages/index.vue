<template>
    <div>
        <Banner :slogan="content.banner_slogan" />

        <TextAndImage
            :image1="require('~/static/DSC_6102pp.jpg')"
            :image2="require('~/static/negative-space-macbook.jpg')"
            :heading="content.about_us_heading"
        >
            <p
                v-html="content.about_us_short_text"
                class="text-gray-500 mb-8"
            ></p>
            <Btn href="/info" />
        </TextAndImage>

        <BlogList title="Przeczytaj" :posts="posts" :num="3" />

        <div class="bg-gray-50 overflow-hidden">
            <!-- <HeaderAndText
                class="text-center"
                title="Co robimy"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
            >
                <p class="text-gray-500 mb-6">
                    Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia.
                </p>
                <Btn />
            </HeaderAndText> -->
            <HeaderAndText
                title="Rekomendacje"
                subtitle="Przeczytaj co o współpracy z nami mówią inni:"
            />
            <Quotes
                :quotes="content.quotes"
            />
        </div>

        <HeaderAndText
            title="Newsletter"
            subtitle="Zapisz się do naszego newslettera"
            :bg-image="require('~/static/kadr.jpg')"
            is-dark
        >
            <Newsletter />
        </HeaderAndText>

        <HeaderAndText
            title="Kontakt"
        />

        <ContactSection />
    </div>
</template>

<script>
import Banner from '~/components/Banner.vue'
import TextAndImage from '~/components/TextAndImage.vue'
import BlogList from '~/components/BlogList.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'
import Quotes from '~/components/Quotes.vue'
import Btn from '~/components/Btn.vue'
import Newsletter from '~/components/Newsletter.vue'
import ContactSection from '~/components/ContactSection.vue'

export default {
    name: 'Home',

    layout: 'layout',

    components: {
        Banner,
        TextAndImage,
        BlogList,
        HeaderAndText,
        Quotes,
        Btn,
        Newsletter,
        ContactSection
    },

    async asyncData() {
        const content = await import('~/content/data/home.json')

        const allPosts = await require.context('~/content/blog-posts/', true, /\.md$/)
        const posts = allPosts.keys().map((key) => allPosts(key))

        return {
            content,
            posts
        }
    }
}
</script>

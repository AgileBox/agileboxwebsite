<template>
    <div>
        <Banner />
        <TextAndImage
            :image1="require('~/static/DSC_6102pp.jpg')"
            :image2="require('~/static/negative-space-macbook.jpg')"
            heading="Kilka słów o nas"
        >
            <p class="text-gray-500 mb-8">Poznałyśmy się 2018 roku w William Hill gdzie prowadziłyśmy wspólnie transformację Agilową w ponad 50 zespołach pracujących w różnych lokalizacjach w Krakowie, Leeds, Londynie i na Gibraltarze. Szybko okazało się, że mamy wiele wspólnego, a szczególnie pasję do dzielenia się wiedzą i wspierania Scrum Masterów, Product Ownerów i managerów w ich codziennej pracy. </p>
            <Btn />
        </TextAndImage>
        <BlogList title="Przeczytaj" :posts="posts" :num="3" />
        <div class="bg-gray-50 pb-10">
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
            <Quotes />
        </div>
        <HeaderAndText
            class="text-center"
            title="Newsletter"
            subtitle="Zapisz się do naszego newlettera"
            :bg-image="require('~/static/kadr.jpg')"
            is-dark
        >
            <Newsletter />
        </HeaderAndText>
        <HeaderAndText
            class="text-center"
            title="Kontakt"
        >
        </HeaderAndText>
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

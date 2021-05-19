<template>
    <div>
        <Banner />
        <TextAndImage
            :image1="require('~/static/DSC_6102pp.jpg')"
            :image2="require('~/static/DSC_6102pp.jpg')"
            heading="Lorem ipsum dolor sit amet consectetur adipisicing elit."
        >
            <p class="text-gray-500 mb-8">Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi?</p>
            <Btn />
        </TextAndImage>
        <BlogList :posts="posts" />
        <div class="bg-gray-50 pb-10">
            <HeaderAndText
                class="text-center"
                title="Co robimy"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
            >
                <p class="text-gray-500 mb-6">
                    Fugit quas, maiores debitis ut beatae quibusdam, dignissimos aliquid aspernatur temporibus tempore non suscipit necessitatibus alias quidem accusantium voluptatum laborum doloribus quasi? Temporibus, repellat, natus fuga labore expedita ducimus perferendis consequatur facere nostrum voluptatum commodi repellendus itaque, quos modi voluptatibus tempora deleniti iure mollitia.
                </p>
                <Btn />
            </HeaderAndText>
            <HeaderAndText
                title="Rekomendacje"
                subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit quas, maiores debitis ut beatae quibusdam."
            />
            <Quotes />
        </div>
        <HeaderAndText
            class="text-center"
            title="Newsletter"
            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
            :bg-image="require('~/static/DSC_6102pp.jpg')"
            is-dark
        >
            <Newsletter />
        </HeaderAndText>
        <HeaderAndText
            class="text-center"
            title="Kontakt"
            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit."
        >
        </HeaderAndText>
        <div class="wrapper grid grid-cols-12 gap-8 mb-16">
            <Card class="col-span-4">
                <div class="flex items-start">
                    <Icon glyph="map" class="text-5xl text-blue-500 mr-8"/>
                    <div>
                        <h4 class="mb-4">Adres</h4>
                        <p class="text-gray-500">ul Jakastam<br>Kraków</p>
                    </div>
                </div>
            </Card>
            <Card class="col-span-4">
                <div class="flex items-start">
                    <Icon glyph="phone-handset" class="text-5xl text-blue-500 mr-8"/>
                    <div>
                        <h4 class="mb-4">Telefon</h4>
                        <p class="text-gray-500">333 654 678<br>666 888 999</p>
                    </div>
                </div>
            </Card>
            <Card class="col-span-4">
                <div class="flex items-start">
                    <Icon glyph="laptop" class="text-5xl text-blue-500 mr-8"/>
                    <div>
                        <h4 class="mb-4">E-mail</h4>
                        <p class="text-gray-500">kontakt@agilebox.pl</p>
                    </div>
                </div>
            </Card>
        </div>
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
import Card from '~/components/Card.vue'
import Icon from '~/components/Icon.vue'

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
        Card,
        Icon
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

<template>
    <section class= "wrapper mt-40 mb-20">
        <h2
            v-if="title"
            class="text-center text-4xl font-bold my-8"
        >
            {{ title }}
        </h2>
        <ul class="grid grid-cols-12 gap-8">
            <li
                v-for="post in sortedPosts"
                :key="post.attributes.title"
                class="col-span-12 md:col-span-4"
            >
                <NuxtLink
                    class="blog-card"
                    :to="`/blog/${formatSlug(post.attributes.title)}`"
                >
                    <div class="overflow-hidden bg-gray-800 mb-6 h-60 rounded-lg shadow-2xl">
                        <img :src="post.attributes.hero_image" :alt="post.attributes.title" class="blog-card__img h-full w-full object-cover opacity-90">
                    </div>
                    <h3 class="text-gray-500 mb-2">{{ formatDate(post.attributes.date) }}</h3>
                    <h2 class="text-2xl font-bold mb-4">{{ post.attributes.title }}</h2>
                    <!-- <p>{{ formatExcerpt(post.body) }}...</p> -->
                    <p class="font-medium text-blue-500">Czytaj więcej</p>
                </NuxtLink>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props: {
        posts: {
            type: Array,
            required: true
        },
        num: Number,
        title: String
    },
    computed: {
        sortedPosts() {
            const sortedPosts = this.posts
            sortedPosts.sort((a,b) => {
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
            return sortedPosts.slice(0, this.num)
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
        formatExcerpt(body) {
            return body.slice(0, 200).trimEnd()
        },
        formatSlug(title) {
            const regex = / /gi;
            return title.toLowerCase().trim().replace(regex, "-")
        }
    }
}
</script>

<style lang="scss">
.blog-card {
    $this: &;

    &__img {
        transition: transform .8s;
    }

    &:hover {
        #{$this}__img {
            transform: scale(1.1)
        }
    }
}
</style>

<template>
    <header
        :class="{
            'bg-gray-800 border-none shadow-lg': isScrolled
        }"
        class="header fixed w-full text-white z-50 border-b border-white border-opacity-20 transition-all duration-300"
    >
        <div class="wrapper h-1/5 flex flex-row justify-between items-center">
            <NuxtLink to="/" class="logo text-2xl font-bold tracking-widest">
                AgileBox
            </NuxtLink>

            <nav class="nav">
                <ul class="flex flex-row">
                    <li
                        v-for="(item, index) in menuItems"
                        :key="index"
                    >
                        <NuxtLink :to="item.to" class="[ block p-6 font-medium hover:text-blue-200 transition-all ] nav__item">
                            {{ item.name }}
                        </NuxtLink>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    props: {
        isScrolled: Boolean,
    },

    data: () => ({
        menuItems: [
            {
                name: "Strona główna",
                to: "/"
            },
            {
                name: "O nas",
                to: "/info"
            },
            // {
            //     name: "Oferta",
            //     to: "/offer"
            // },
            {
                name: "Blog",
                to: "/blog"
            },
            {
                name: "Kontakt",
                to: "/contact"
            },
        ]
    })
}
</script>

<style lang="scss">
.nav__item {
    position: relative;

    &::after {
        content: "";
        position: absolute;
        left: 0;
        bottom: 0;
        width: 0;
        height: 2px;
        background-color: rgb(191, 219, 254);
        transition: all .3s;
        opacity: 0;
    }

    &:hover {
        &::after {
            width: 100%;
            opacity: 1;
        }
    }
}
</style>

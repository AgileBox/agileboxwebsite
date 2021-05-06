<template>
    <header class="header fixed w-full z-50 border-b border-gray-500 border-opacity-25">
        <div class="wrapper h-1/5 flex flex-row justify-between items-center">
            <div class="logo">
                Logo
            </div>

            <nav class="nav">
                <ul class="flex flex-row">
                    <li
                        v-for="(item, index) in menuItems"
                        :key="index"
                    >
                        <NuxtLink :to="item.to" class="[ block p-6 font-medium hover:text-blue-700 transition-all ] nav__item">
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
    data: () => ({
        menuItems: [
            {
                name: "Strona główna",
                to: "/"
            },
            {
                name: "O nas",
                to: "/"
            },
            {
                name: "Oferta",
                to: "/"
            },
            {
                name: "Blog",
                to: "/"
            },
            {
                name: "Kontakt",
                to: "/"
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
        width: 0;
        height: 2px;
        background-color: black;
        left: 0;
        bottom: 0;
        transition: all .2s;
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

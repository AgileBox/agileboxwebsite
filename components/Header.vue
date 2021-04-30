<template>
    <header class="header fixed w-full z-50">
        <div class="wrapper h-1/5 flex flex-row justify-between items-center">
            <div class="logo">
                Logo
            </div>

            <nav class="nav">
                <ul class="flex flex-row">
                    <li
                        v-for="(item, index) in menuItems"
                        class="nav__items"
                        :key="index"
                    >
                        <NuxtLink :to="item.to" class="block p-6">
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

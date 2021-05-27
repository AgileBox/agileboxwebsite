<template>
    <nav aria-label="Breadcrumb" class="breadcrumbs p-4">
        <ul class="flex">
            <li
                v-for="(item, itemIndex) in items"
                :key="itemIndex"
                class="flex text-white text-xs"
            >
                <a
                    v-if="item.href"
                    :href="item.href"
                    class="text-white text-opacity-60 p-2 hover:text-blue-200 transition-all duration-200"
                >
                    {{ item.name }}
                </a>
                <span v-else class="p-2">
                    {{ item.name }}
                </span>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    props: {
        items: Array
    }
}
</script>

<style lang="scss">
.breadcrumbs {
    ul {
        li {
            &::after {
                content: '';
                display: inline-block;
                margin: 0 14px;
                width: 1px;
                height: 80%;
                background-color: #fff;
                opacity: .6;
                transform: rotate(30deg);
            }

            &:last-child {
                &::after {
                    display: none;
                }
            }

            a {
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
                        color: rgb(191, 219, 254);
                        width: 100%;
                        opacity: 1;
                    }
                }
            }
        }
    }
}

</style>

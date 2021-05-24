<template>
    <nav aria-label="Breadcrumb" class="breadcrumbs">
        <ul>
            <li v-for="(item, itemIndex) in items" :key="itemIndex">
                <a v-if="item.href" :href="item.href">
                    {{ item.name }}
                </a>
                <span v-else>
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
        padding: 10px;

        ul {
            display: flex;

            li {
                display: flex;
                color: #fff;
                font-size: .8rem;

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
                color: #fff;
                opacity: .6;
                transition: .2s;

                &:hover {
                    color: rgb(59, 130, 246);
                }
            }
        }
    }
}

</style>

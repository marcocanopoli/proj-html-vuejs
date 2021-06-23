<template>
    <section class="news dark-text">
        <div class="container">
            <SectionTitle :section-title="Title"/>
            <div class="news-cards">
                <TheNewsCard 
                    v-for="item in news"
                    :key="item.pic"
                    :item="item"/>
            </div>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import TheNewsCard from './TheNewsCard.vue';
import news from '../data/news.js';

export default {
    name: 'TheNews',
    components: {
        SectionTitle,
        TheNewsCard
    },
    data() {
        return {
            Title: {
                class: 'section-dark-title',
                subtitle: 'Our editorial content',
                titleHTML: 'Latest <span>News</span>',
                firstText: 'Every week we publish content about what is best in the business world.',
                button: {
                    class: "button button-solid",
                    url: "#",
                    text: "See all"
                }
            },
            news
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/mixins.scss';

    .news-cards {
        @include flex-wrap-between;
    }
</style>
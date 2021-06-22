<template>
    <section class="dark-text">
        <div class="container">
            <SectionTitle :sectionTitle="Title"/>
            <div class="news">
                <NewsCard 
                    v-for="item in news"
                    :key="item.pic"
                    :item="item"/>
            </div>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import NewsCard from './NewsCard.vue';
import news from '../data/news.js';

export default {
    name: 'TheNews',
    components: {
        SectionTitle,
        NewsCard
    },
    data() {
        return {
            Title: {
                class: 'section-dark-title',
                subtitle: 'Our editorial content',
                titleHTML: 'Latest <span>News</span>',
                firstText: 'Every week we publish content about what is best in the business world.',
                button: {
                    class: "btn btn-solid",
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

    .news {
        @include flex-wrap-between;
    }
</style>
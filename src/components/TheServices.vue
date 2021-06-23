<template>
    <section class="services dark-text">
        <div class="container">
            <SectionTitle :section-title="Title"/>

            <!-- Option cards -->
            <div class="services-cards">
                <TheServicesCard 
                    v-for="item, index in services"
                    :key="index"
                    :option="item"/>
            </div>
            <!-- /Option cards -->
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import TheServicesCard from './TheServicesCard.vue';
// import services from '../data/links/services.js'

export default {
    name: 'TheServices',
    components: {
        SectionTitle,
        TheServicesCard
    },
    data() {
        return {
            Title: {
                class: 'section-dark-title',
                subtitle: 'Our business areas',
                titleHTML: 'Excellence in <span>Services</span>',
                firstText: 'We are leaders in providing consultancy services with a set of cutting-edge technologies and a team of experienced and renowned professionals. These are some options that you can hire.',
                button: {
                    class: "button button-solid",
                    url: "#",
                    text: "See all"
                }
            }
        }
    }, props: {
        services: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .services {
        background-color: $bg-light-col;
    }

    .services-cards {
        @include flex-wrap-between;
    }

</style>
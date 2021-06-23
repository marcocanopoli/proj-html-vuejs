<template>
    <section class="company light-text">
        <div class="container">            
            <SectionTitle :section-title="Title"/>

            <!-- company strenghts -->
            <div class="company-cards ">
                <TheCompanyCard 
                    v-for="item, index in companyStrengths"
                    :key="index"
                    :item="item"/>                
            </div>
            <!-- company strenghts -->
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue'
import TheCompanyCard from './TheCompanyCard.vue'
import companyStrengths from '../data/company-strenghts.js'

export default {
    name: 'TheCompany',
    components: {
        SectionTitle,
        TheCompanyCard
    },
    data() {
        return {
            Title: {
                class: 'section-light-title',
                subtitle: 'About the network',
                titleHTML: '<span>The</span> Company',
                firstText: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit exercitationem sint quisquam accusamus unde, earum numquam dolores modi, inventore debitis.',
                secondText: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia in minus adipisci eius, pariatur et.'
            },
            companyStrengths
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .company {
        background-color: $bg-col;
    }

    .container {
        @include flex-center ('both');
        justify-content: space-between;
        height: 100%;

        & > div {
            width: calc((100% - 60px) / 2);                
        }
    }

    .company-cards {
        @include flex-wrap-between;
        margin-left: 90px;
    }

</style>
<!-- 'class' refers to global 'section-dark-title' and 'section-light-title' -->
<!-- h2 and paragraphs display HTML content -->

<template>
    <div class="title" 
        :class="sectionTitle.class">
        <h5>{{ sectionTitle.subtitle }}</h5>
        <h2 v-html="sectionTitle.titleHTML"></h2>
        <div v-if="sectionTitle.button"
            class="description">
            <div>
                <p  v-html="sectionTitle.firstText"></p>
                <p  v-if="sectionTitle.secondText"
                    v-html="sectionTitle.secondText"></p>
            </div>
            <a  :class="sectionTitle.button.class" 
                :href="sectionTitle.button.url">
                {{ sectionTitle.button.text}}
            </a>
        </div>
        <div v-else>
            <p  v-html="sectionTitle.firstText"></p>
            <p  v-if="sectionTitle.secondText"
                v-html="sectionTitle.secondText"></p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SectionTitle',
    props: {
        sectionTitle: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';
    
    div > * {
        margin-bottom: 20px;

        .description {
            @include flex-center ('cross');
            justify-content: space-between;

            div {
                width: 80%;
            }
        }
    }

</style>
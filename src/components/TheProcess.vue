<template>
    <section class="light">
        <div class="container">
            <SectionTitle :sectionTitle="Title"/>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';

export default {
    name: 'TheProcess',
    components: {
        SectionTitle
    },
    data() {
        return {
            Title: {
                class: 'section-dark-title',
                subtitle: 'How it works in practice',
                titleHTML: '<span>Process</span> Management',
                firstText: 'We work with innovative methodologies to ensure that the entire reformatting process is done from start to finish as planned.'
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .container {
        width: 40%;
        text-align: center;
    }

</style>
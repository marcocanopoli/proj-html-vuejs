<template>
    <section class="dark-text">
        <div class="container">
            <SectionTitle :sectionTitle="Title"/>
        </div>
        <div class="steps">
            <ProcessStep
                v-for="step in steps"
                :key="step.stepNum"
                :step="step"/>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import ProcessStep from './ProcessStep.vue';
import steps from '../data/process-steps.js';

export default {
    name: 'TheProcess',
    components: {
        SectionTitle,
        ProcessStep
    },
    data() {
        return {
            Title: {
                class: 'section-dark-title',
                subtitle: 'How it works in practice',
                titleHTML: '<span>Process</span> Management',
                firstText: 'We work with innovative methodologies to ensure that the entire reformatting process is done from start to finish as planned.'
            },
            steps
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .container {
        width: 40%;
        margin-bottom: 50px;
        text-align: center;
    }

    .steps {
        @include flex-center ('main');
        position: relative;

        &::before{
            position: absolute;
            top: 23px;
            left: 0;
            transform: translateY(-50%);
            content: '';
            height: 5px;
            width: 100%;
            background-color: $brand-light-col;
            z-index: -1;
        }
    }

</style>
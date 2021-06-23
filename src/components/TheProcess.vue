<template>
    <section class="process dark-text">
        <div class="container">
            <Section-title :section-title="Title"/>
        </div>
        <div class="steps">
            <TheProcessStep
                v-for="step in steps"
                :key="step.stepNum"
                :step="step"/>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import TheProcessStep from './TheProcessStep.vue';
import steps from '../data/process-steps.js';

export default {
    name: 'TheProcess',
    components: {
        SectionTitle,
        TheProcessStep
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
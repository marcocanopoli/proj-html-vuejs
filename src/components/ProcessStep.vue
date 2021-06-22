<template>
    <div class="step">
        <span>{{ step.stepNum }}</span>
        <h3>{{ step.title }}</h3>
        <p>{{ step.text }}</p>
    </div>
</template>

<script>
export default {
    name: 'ProcessStep',
    props: {
        step: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';

    .step { 
        position: relative;
        width: 250px;      
        margin: 0 30px 20px;
        text-align: center;

        &:hover {
            span {
                color: $text-col;
                background-color: $brand-col;
                transform: scale(130%);
            }
        }

        span {
            display: inline-block;            
            height: 46px;
            width: 46px;
            line-height: 46px;
            font-size: 20px;
            font-weight: 700;
            vertical-align: middle;
            border-radius: 50%;
            color: $brand-dark-col;
            background-color: $brand-light-col;
            transition: $trans-time;
        }

        h3 {
            margin: 20px 0;
        }
    }
</style>
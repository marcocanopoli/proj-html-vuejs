<template>
    <div class="option">
        <div>
            <i :class="option.icon"></i>
            <a :href="option.url">
                <i class="fas fa-arrow-right"></i>
            </a>            
        </div>        
        <h3>{{ option.text }}</h3>
        <p>{{ option.description }}</p>
    </div>
</template>

<script>
export default {
    name: 'OptionCard',
    props: {
        option: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';

    .option {
        width: calc((100% - 60px) / 3);
        margin-bottom: 30px;
        padding: 50px;
        border-radius: 10px;
        background-color: #fff;

        div {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;

            i {
                font-size: 48px;
                color: $brand-dark-col;

                &.fa-arrow-right {
                    font-size: 24px;
                    color: $brand-dark50-col;
                }
            }
        }

        h3, p {
            margin-bottom: 20px;
        }
    }
</style>
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
    name: 'TheServicesCard',
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
        transition: $trans-time;

        &:nth-last-child(-n+3) {
            margin-bottom: 0;
        }

        &:hover {
            transform: $move-card-up;
            box-shadow: 0 5px 5px $black10;
        }


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
                    transition: $trans-time;

                    &:hover {
                        transform: scale(200%);
                        color: $brand-dark-col;
                    }
                }
            }
        }

        h3, p {
            margin-bottom: 20px;
        }
    }
</style>
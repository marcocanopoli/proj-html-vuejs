<template>
    <div class="company-card">
        <i :class="item.icon"></i>
        <h3>{{ item.title }}</h3>
        <p>{{ item.text }}</p>
    </div>
</template>

<script>
export default {
    name: 'TheCompanyCard',
    props: {
        item: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    
    .company-card {
        width: calc((100% - 30px) / 2);
        margin-bottom: 60px;
        
        &:nth-last-child(-n+2) {
            margin-bottom: 0;
        }

        i {
            font-size: 26px;
            color: $brand-col;
            margin-right: 10px;
        }

        h3 {
            display: inline-block;
            margin-bottom: 15px;
        }
    }
</style>
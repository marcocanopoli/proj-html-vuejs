<template>
    <main>
        <Company />
        <Services />
    </main>
</template>

<script>
import Company from './Company.vue';
import Services from './Services.vue';

export default {
    name: 'Main',
    components: {
        Company,
        Services
    }
}
</script>

<style lang="scss" scoped>    

</style>
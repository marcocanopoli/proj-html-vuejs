<template>
    <main>
        <TheCompany />
        <TheServices />
        <TheProcess />
    </main>
</template>

<script>
import TheCompany from './TheCompany.vue';
import TheServices from './TheServices.vue';
import TheProcess from './TheProcess.vue';

export default {
    name: 'TheMain',
    components: {
        TheCompany,
        TheServices,
        TheProcess
    }
}
</script>

<style lang="scss" scoped>    

</style>
<template>
    <main>
        <TheCompany />
        <TheServices 
            :services="servicesLinks"/>
        <TheProcess />
        <TheTeam />
        <TheNews />
        <TheNewsletter />
    </main>
</template>

<script>
import TheCompany from './TheCompany.vue';
import TheServices from './TheServices.vue';
import TheProcess from './TheProcess.vue';
import TheTeam from './TheTeam.vue';
import TheNews from './TheNews.vue';
import TheNewsletter from './TheNewsletter.vue';

export default {
    name: 'TheMain',
    components: {
        TheCompany,
        TheServices,
        TheProcess,
        TheTeam,
        TheNews,
        TheNewsletter
    },
    props: {
        servicesLinks: Array
    }
}
</script>

<style lang="scss">    

</style>
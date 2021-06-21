<template>
  <div id="app">
    <TheHeader />
    <TheMain />
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';
import TheFooter from './components/TheFooter.vue';
//font
import "@fontsource/poppins";

export default {
  name: 'App',
  components: {
    TheHeader,
    TheMain,
    TheFooter
  }
}
</script>

<style lang="scss">
  @import './assets/style/global.scss';

</style>

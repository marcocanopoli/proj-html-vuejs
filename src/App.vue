<template>
  <div id="app">
    <TheHeader />
    <TheMain 
      :servicesLinks="servicesLinks"/>
    <TheFooter 
      :servicesLinks="servicesLinks"/>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';
import TheFooter from './components/TheFooter.vue';

//font
import "@fontsource/poppins";

import servicesLinks from './data/links/services.js'

export default {
  name: 'App',
  components: {
    TheHeader,
    TheMain,
    TheFooter
  },
  data() {
    return {
      servicesLinks
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/global.scss';

</style>

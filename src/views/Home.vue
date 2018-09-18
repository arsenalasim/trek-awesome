<template>
  <div class="home">
    <header-banner></header-banner>
    <product-list></product-list>
    <info-section></info-section>
    <my-footer></my-footer>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import HeaderSection from '../container/LandingPage/HeaderSection.vue';
import ProductSection from '../container/LandingPage/ProductSection.vue';
import InfoSection from '../container/LandingPage/InfoSection.vue';
import FooterSection from '../container/LandingPage/FooterSection.vue';


export default {
  name: 'home',
  components: {
    // HelloWorld
    HeaderSection,
    ProductSection,
    InfoSection,
    FooterSection

  }
}
</script>

<style scoped>
  .home{
    margin: 0;
    padding: 0;
    width: 100%;
    height: auto;
    background-color: #7a8cde;
  }
</style>


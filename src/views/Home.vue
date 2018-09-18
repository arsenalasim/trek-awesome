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

import HeaderBanner from '../container/LandingPage/HeaderBanner.vue';
import ProductList from '../container/LandingPage/ProductList.vue';
import InfoSection from '../container/LandingPage/InfoSection.vue';
import MyFooter from '../container/LandingPage/MyFooter.vue';


export default {
  name: 'home',
  components: {
    // HelloWorld
    HeaderBanner,
    ProductList,
    InfoSection,
    MyFooter

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


<template>
    <div id="product">
        <product-menu></product-menu>
        

    </div>
    
</template>

<script>
    import ProductMenu from '../../components/ProductList/ProductMenu.vue';

    export default {
        components:{
            ProductMenu
        }

    }
    
</script>

<style scoped>
    #product{
        min-height: 700px;
        background-color: #a1a8ee;
        margin:0;
    }
</style>
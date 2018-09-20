<template>
    <div id="head">
        <accounts></accounts>
        <my-menu></my-menu>
        <carousel></carousel>
        <services></services>
        

    </div>
    
</template>

<script>
    import Accounts from '../../components/Header/Accounts.vue';
    import MyMenu from '../../components/Header/MyMenu.vue';
    import Carousel from '../../components/Header/Carousel.vue';
    import Services from '../../components/Header/Services.vue';

    export default {
        components:{
            Accounts,
            MyMenu,
            Carousel,
            Services
        }
    }
    
</script>

<style scoped>
#head{
    height: 600px;
    display:flex;
    flex-direction: column;
    align-items: center;

     background-color:white;
    /* background-image: url('../../assets/bg-image3.jpg'); */
   
}


</style>


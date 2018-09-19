<template>
    <div id="head">
        <accounts></accounts>
        <my-menu></my-menu>
        

    </div>
    
</template>

<script>
    import Accounts from '../../components/Header/Accounts.vue';
    import MyMenu from '../../components/Header/MyMenu.vue';

    export default {
        components:{
            Accounts,
            MyMenu
        }
    }
    
</script>

<style scoped>
#head{
    height: 550px;
    display:flex;
    flex-direction: column;
    align-items: center;

    /* background-color: #9dedbb; */
    background-image: url('../../assets/bg-image3.jpg')
    
}


</style>


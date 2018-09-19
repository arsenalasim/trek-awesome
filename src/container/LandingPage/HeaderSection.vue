<template>
    <div id="head">
        <accounts></accounts>
        

    </div>
    
</template>

<script>
    import Accounts from '../../components/Header/Accounts.vue';

    export default {
        components:{
            Accounts
        }
    }
    
</script>

<style scoped>
#head{
    min-height: 500px;
    background-color: #9dedbb;
}


</style>


<template>
    <div id="#accounts">
        
        <div id="logo">
            <img :src="image" alt="company logo">
            
        </div>
        <div id="account-options">

        </div>
    </div>
</template>

<script>
import logo1 from '../../assets/logo1.png'
export default {
    data:function(){
        return{
            image:logo1
        }
    }
}
</script>

<style scoped>
    img{
        height: 100px;
        width: 100px;
    }
</style>




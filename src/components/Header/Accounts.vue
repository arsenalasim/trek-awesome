<template>
    <div id="accounts">
        
        <div id="logo">
            <img :src="image" alt="company logo">
            <h2>Trek Awesome</h2>
            
        </div>
        <div id="account-options">
            <p class="button">My account</p>
            <p class="button">Sign up</p>
            <p class="button">Sign in</p>

        </div>
    </div>
</template>

<script>
import logo3 from '../../assets/logo3.png'
export default {
    data:function(){
        return{
            image:logo3
        }
    }
}
</script>

<style scoped>

    img{
        height: 50px;
        width: 100px;
        margin: 5px;
    }

    #accounts{
        display: flex;
        justify-content: space-between;
        margin-top: 0px;
        height: 60px;
        width: 90%;
    }

    #logo{
        display: flex;
    }

    #logo h2 {
        margin-left: 10px;
    }

    #account-options{
        width: 25%;
        display:flex;
        justify-content: space-around;
        align-items: center;
    }

    .button{
        background-color: #93c2d6;
        border-radius: 5px;
        color:#143996;
        padding: 10px 20px;
        margin: 0px auto;
            
    }
    p.button:hover{
        background-color: #143996;
        color: #93c2d6;
    }
    
</style>




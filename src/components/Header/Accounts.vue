<template>
    <div id="accounts">
        
        <div id="logo">
            <img :src="image" alt="company logo">
            <h2>Trek Awesome</h2>
            
        </div>
        <div id="account-options">
            <p class="button">ACCOUNT</p>
            <p class="button">SIGN UP</p>
            <p class="button">SIGN IN</p>

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
        background-color: #cccccc;
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
        height: 100%;
        align-items: center;
    }

    .button{
        width:33.33%;
        height: 100%;
        box-sizing: border-box;
        background-image: linear-gradient(to right,#cbcccc,#babbbb);
        border-style: none;
        color:#414b4f;
        padding: 25px 20px;
        margin: 0;
            
    }
    p.button:hover{
        background-image:linear-gradient(to bottom,#cbcccc,#babbbb);
        color: white;
    }
    
</style>




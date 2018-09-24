<template>
    <div id="accounts">
        
        <div id="logo">
            <img :src="image" alt="company logo">
            <h2>Trek Awesome</h2>
            
        </div>
        <div id="account-options">
            <p class="button">ACCOUNT</p>
            <p class="button" onclick="document.getElementById('signup').style.display='block'">SIGN UP</p>
            <p class="button" onclick="document.getElementById('signin').style.display='block'">SIGN IN</p>

        </div>
        <signup-modal id="signup"></signup-modal>
        <signin-modal id="signin"></signin-modal>

    </div>
</template>

<script>
import logo3 from '../../assets/logo3.png';
import SigninModal from './SigninModal.vue';
import SignupModal from './SignupModal.vue';

export default {
    data:function(){
        return{
            image:logo3
        }
    },

    components:{
        SigninModal,
        SignupModal
    }
}
</script>

<style scoped>

    img{
        height: 35px;
        width: 80px;
        padding: 5px 5px 0 5px;
        
        background: #6a7fac;
    }

    #accounts{
        /* background-color: #0579a7; */
         background: #6a7fac;
        display: flex;
        justify-content: space-between;
        margin-top: 0px;
        height: 40px;
        width: 100%;
    }

    #logo{
        display: flex;
    }

    #logo h2 {
        margin: 5px 5px 5px 10px;
        color:#ffffff;
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
        background-image: linear-gradient(to right,#6a7fac,#788ab4);
        border-style: none;
        color:#dddddd;
        padding: 10px 20px;
        margin: 0;
            
    }

    p{
        font-size: 14px;
    }
    p.button:hover{
        background-image:linear-gradient(to bottom,#748ec7,#8aa3d8);
        color: white;
        cursor: pointer;
    }
    
</style>




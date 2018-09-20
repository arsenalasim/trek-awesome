<template>
    <div id="menu">
        <p><img :src="home" alt="home button">Home</p>
        <p><img :src="category" alt="category button">Categories</p>
        <div>
            <img :src="search" alt="search icon">
            <input type="text" placeholder="Search..." >
        </div>
        <p>
         <img :src="wish" alt="wish list"> <span>Wish List</span> 
        </p>
        <p>
        <img :src="cart" alt="cart"><span> My Cart</span>
        </p>

    </div>
    
</template>

<script>
import cart3 from '../../assets/cart3.png'
import wish7 from '../../assets/wish7.png'
import home4 from '../../assets/home4.png'
import category4 from '../../assets/category4.png'
import search6 from '../../assets/search6.png'

export default {
    data:function(){
        return{
            home: home4,
            category: category4,
            cart: cart3,
            wish: wish7,
            search: search6

        }
    }
}
</script>

<style scoped>

    #menu{
        display:flex;
        justify-content: space-between;
        align-items: center;
        height: 50px;
        width: 90%;
        background: #93c2d6;
    }

    #menu img{
        height: 40px;
        width:40px;
    }

    #menu p{
        background-color: #c3e1ee;
        color: #143996;
        border-radius: 20px;
        display:flex;
        align-items: center;
        width:10%;
        margin: 0 15px;
    }

    #menu div{
        background-color: #c3e1ee;
        border-radius: 20px;
        display:flex;
        align-items: stretch;
       
        width:50%;
        margin: 0 15px;
    }

    #menu input[type="text"]{
        background-color:#c3e1ee;
        border-style: none;
        border-top-right-radius: 20px;
        border-bottom-right-radius: 20px;
        width:90%;
        height: 30px;
        font-size: 18px;
        padding:5px;
       
       
      
    }

</style>



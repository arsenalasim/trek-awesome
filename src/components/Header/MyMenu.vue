<template>
    <div id="menu">
        <p><img :src="home" alt="home button">Home</p>
        <p><img :src="category" alt="category button" style="padding-left:0;">Categories</p>
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
import cart2 from '../../assets/cart2.png'
import wish8 from '../../assets/wish8.png'
import home12 from '../../assets/home12.png'
import category7 from '../../assets/category7.png'
import search2 from '../../assets/search2.png'

export default {
    data:function(){
        return{
            home: home12,
            category: category7,
            cart: cart2,
            wish: wish8,
            search: search2

        }
    }
}
</script>

<style scoped>

    #menu{
        display:flex;
        justify-content: space-between;
        align-items: center;
        height: 60px;
        width: 100%;
        background: #02c39a;
        position: sticky;
        top:0px;
    }

    #menu img{
        height: 30px;
        width:35px;
        padding: 0 10px;
        color: white;
    }

    #menu p{
        background:#02c39a;
        color: #eeeeee;
        font-weight: bold;
        display:flex;
        align-items: center;
        width:10%;
        margin: 0 15px;
        transition: transform 0.2s;
    }

    #menu p:hover{
        transform:scale(1.2);
        background-image:linear-gradient(to right,#02c39a,#31dfb9);
        cursor: pointer;
        color:white;
    }

    #menu div{
        background-color: #dedede;
        
        display:flex;
        align-items: stretch;
       
        width:50%;
        margin: 0 15px;
    }

    #menu input[type="text"]{
        background-color:#dedede;
        border-style: none;
        
        width:90%;
        height: 20px;
        font-size: 18px;
        padding:5px;
       
       
      
    }

</style>



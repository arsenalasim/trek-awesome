<template>
    <div id="menu">
        <p><img :src="home" alt="home button">Home</p>
        <div id="dropdown">
            <p id="categorybtn"><img :src="category" alt="category button" style="padding-left:0;">Categories</p>
            <category-dropdown class="dropdown-content"></category-dropdown>
        </div>
        <div id="searchbar">
            <img :src="search" alt="search icon" style="height:22px; width:22px; padding:5px;">
            <input type="text" placeholder="Search..." >
        </div>
        <p>
         <img :src="wish" alt="wish list"> <span>Wish List</span> 
        </p>
        <p onclick="document.getElementById('cart').style.display='block'">
        <span id="token">{{count}}</span><img :src="cart" alt="cart"><span>Cart</span>
        </p>

        <cart-modal id="cart"></cart-modal>

    </div>
    
</template>

<script>
import cart2 from '../../assets/cart2.png'
import wish8 from '../../assets/wish8.png'
import home12 from '../../assets/home12.png'
import category7 from '../../assets/category7.png'
import search7 from '../../assets/search7.png'
import CategoryDropdown from './CategoryDropdown.vue'
import CartModal from './CartModal.vue';

export default {
    data:function(){
        return{
            home: home12,
            category: category7,
            cart: cart2,
            wish: wish8,
            search: search7,
            count:0

        }
    },

    components:{
        CategoryDropdown,
        CartModal
    },
     created(){
            this.$eventBus.$on('increase-count',()=>{
                this.count+=1;
            });
        }
}
</script>

<style scoped>

    #menu{
        display:flex;
        justify-content: space-between;
        align-items: center;
        height: 50px;
        width: 100%;
        background: #7eb5cc;
        /* background: #16d6ad; */
        /* background-color: #0579a7; */
        /* background: #48639c; */
        
        position: sticky;
        top:0px;
        z-index: 1;
    }

    #menu img{
        height: 22px;
        width:25px;
        padding: 0 10px;
        
        /* filter: invert(100%); */
        filter: invert(28%) sepia(54%) saturate(1047%) hue-rotate(157deg) brightness(100%) contrast(98%);
    }

    #menu p{
        /* background: #16d6ad; */
        /* background:#02c39a; */
        /* background: #48639c; */
        /* background-color: #0579a7; */
        background: #7eb5cc;
        color: #eeeeee;
        /* font-weight: bold; */
        display:flex;
        align-items: center;
        width:10%;
        margin: 0 10px;
        transition: transform 0.2s;
    }

    #token{
        height: 20px;
        width: 20px;
        color:white;
        background: lightsalmon;
        border-radius:50%;
        padding-top: 2px;
      
    }

    #dropdown p{
         /* background:#16d6ad; */
        /* background: #48639c; */
        /* background-color: #0579a7; */
        background: #7eb5cc;
        color: #eeeeee;
        /* font-weight: bold; */

        display: flex;
        align-items: center;
        width:100%;
        margin: 0 15px;
        transition: transform 0.2s;

    }

    #menu p:hover{
        transform:scale(1.1);
        /* background-image:linear-gradient(to right,#0579a7,#268eb8); */
        background-image:linear-gradient(to right,#7eb5cc,#acd6e7);
        cursor: pointer;
        color:white;
    }

    #searchbar{
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

    #dropdown p{
        overflow: hidden;
       
    }

    .dropdown-content{
        display:none;
        position: absolute;
        z-index: 1;
        width:200px;
        color: #005694;
    }

    #dropdown:hover .dropdown-content{
        display:block;
        background:rgba(220,220,220,0.9);

        
    }


</style>



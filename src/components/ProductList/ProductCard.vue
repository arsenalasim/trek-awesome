<template>
    <div id="product-card">
        <div id="selected" :style="{display:displayScreen}">
            <p>Added to the cart</p>
            <!-- <button @click="removeFromCart()">Remove</button> -->
        </div>
        <h2 id="product-title">{{description}}</h2>
        <img id="product-image" :src="imageurl" alt="product image">
        <div id="card-buttons">
            <button id="wish"><img src="../../assets/wish9.png" alt="heart"></button>
            <button id="cart" @click=" $emit('toggle-selected');  addToCart();"><img src="../../assets/cart10.png" alt="cart"></button>

        </div>
        <p id="price">Rs: {{price}}</p>

        
    </div>
    
</template>

<script>
// import jacket1 from '../../assets/jacket1.jpg'

export default {
    data:function(){
        return{
            
            
        }
    
    },
    props:[
        'description',
        'price',
        'imageurl',
        'selected',
        'cate',
        'index'
        
    ],
    computed:{
        displayScreen:{
            get:function(){
            if(this.selected){
                return "block";
            }else{
                return "none";
            }
        },
        set:function(val){
            return val;
        }
        }

    },

    methods:{
        // increaseCount:function(){
        //     this.$eventBus.$emit('increase-count');
        // },

        // removeFromCart:function(){
        //     this.displayScreen="none";
        // },

        addToCart:function(){
           
            this.$eventBus.$emit('add-to-cart',{name:this.description,quantity:1,price:this.price,imageurl:this.imageurl,myObj:this});
            
        }
    }
    // ,
    // created:function(){
    //         this.$eventBus.$on("remove-from-cart",this.removeFromCart);       
    // }
    
}
</script>

<style scoped>
    *{
        margin:0;
        padding:0;
    }

    #product-card{
        margin:15px 10px;
        padding:5px;
        width: 20%;
        /* height: 350px; */
        border: none;
        box-shadow: 0 0 10px 3px #b1b6b5;
        background: #c5dce6;
        display:flex;
        flex-direction: column;
        justify-content:center;
        align-items: center;
        transition: 0.2s;
        position: relative;
        
      
    }

    #product-card:hover{
        transform: scale(1.05);
        cursor: pointer;
    }

    #selected{
        display: none;
        position: absolute;
        top: 70%;
        left: 0;
       
        height:30%;
        width:100%;
        box-sizing: border-box;
        background:rgba(80,80,80,0.8);
        color: rgb(255, 164, 164);
        text-align: center;
        font-weight: bold;
        font-size: 20px;
       padding-top: 45px;
       /* z-index: 1; */

    }

    #selected button{
        width:50%;
        
        color:white;
        background:rgb(245, 90, 90);
        padding:10px;
        margin:10px;
        border-style: none;
        font-size: 18px;
    }

    #selected button:hover{
        background: rgb(243, 58, 58);
    }


    #product-image{
        width:90%;
        height:220px;
        transition: 0.3s;
    }

    /* #product-image:hover{
        transform: scale(1.1);
        cursor: pointer;

    } */

    #card-buttons{
        width: 95%;
        margin: 5px;
       
    }

    #card-buttons img{
        width: 35px;
        height: 35px;
      
        margin:0;
        padding:0;
       
    }



    #card-buttons button{
        box-sizing: border-box;
        width:45%;
        height:40px;
        margin: 5px 3px;
        border-style: none;
        background: #9fcbdd;
        border-radius: 2px;

    }

    #card-buttons button:hover{
        box-shadow: 0 0 10px 1px #f1938c;
        background: #c5dce6;
        cursor: pointer;
    }

    #price{
        margin: 5px auto;
        color: #013449;
        font-weight: bold;
        background:#9fcbdd;
        border-radius: 2px;
        width:90%;
        height:50px;
        display:flex;
        align-items: center;
        justify-content: center;
        font-size: 20px;
    }

    #price:hover{
        color:#9fcbdd;
        background:#013449;
    }


    #product-title{
        padding: 5px;
        color: #013449;


    }

</style>

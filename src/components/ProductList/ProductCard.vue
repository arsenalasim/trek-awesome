<template>
    <div id="product-card">

        <h2 id="product-title">{{description}}</h2>
        <img id="product-image" :src="imageurl" alt="product image">
        <div id="card-buttons">
            <button id="wish"><img src="../../assets/wish9.png" alt="heart"></button>
            <button id="cart"><img src="../../assets/cart10.png" alt="cart"></button>

        </div>
        <p id="price">Rs: {{price}}</p>

        
    </div>
    
</template>

<script>
// import jacket1 from '../../assets/jacket1.jpg'

export default {
    data:function(){
        return{
        //    myimage:"../../assets/jacket1.jpg",
        //    jacket1

        }
    
    },
    props:[
        'description',
        'price',
        'imageurl'
    ]

    //, methods:{
    //     getImageUrl(){
    //         return this.myimage
    //     }
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
        box-shadow: 0 0 15px 4px #a7b4b1;
        background: #c5dce6;
        display:flex;
        flex-direction: column;
        justify-content:center;
        align-items: center;
         transition: 0.3s;
    }

    #product-card:hover{
        transform: scale(1.1);
        cursor: pointer;
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

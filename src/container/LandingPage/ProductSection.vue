<template>
    <div id="product">
    
        <product-menu></product-menu>
        <div id="cards">
           
                <product-card v-for="item in ProductList" :key="item.title" :description="item.title"
                 :price="item.price" :imageurl="item.imageurl"></product-card>
        
        </div>
        

    </div>
    
</template>

<script>
    import ProductMenu from '../../components/ProductList/ProductMenu.vue';
    import ProductCard from '../../components/ProductList/ProductCard.vue';

    export default {
        data:function(){
            return{
                ProductList:[

                    
                            {title:"Jacket-A",price:"3000",imageurl:require("../../assets/jacket1.jpg")},
                            {title:"Jacket-B",price:"2000",imageurl:require("../../assets/jacket2.jpg")},
                            {title:"Jacket-C",price:"3500",imageurl:require("../../assets/jacket3.jpg")},
                            {title:"Jacket-D",price:"2500",imageurl:require("../../assets/jacket4.jpg")},
                            {title:"Jacket-E",price:"3000",imageurl:require("../../assets/jacket5.jpg")},
                            {title:"Jacket-F",price:"3300",imageurl:require("../../assets/jacket6.jpg")},
                            {title:"Jacket-G",price:"2700",imageurl:require("../../assets/jacket7.jpg")},
                            {title:"Jacket-H",price:"3500",imageurl:require("../../assets/jacket8.jpg")}
                        ] 

                
            }
        },
        components:{
            ProductMenu,
            ProductCard
        }

    }
    
</script>

<style scoped>
    #product{
        min-height: 700px;
        background-color: #d9e9e5;
        margin:0;
        color:white;
       
    }

    #cards{
        margin:10px;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }
</style>
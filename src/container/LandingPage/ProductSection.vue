<template>
    <div id="product">
    
        <product-menu></product-menu>
        <div id="cards">
           
                <product-card v-for="item in ProductList[cat][name[cat]]" :key="item.title" :description="item.title"
                 :price="item.price" :imageurl="item.imageurl"></product-card>
        
        </div>
        

    </div>
    
</template>

<script>
    
    import ProductMenu from '../../components/ProductList/ProductMenu.vue';
    import ProductCard from '../../components/ProductList/ProductCard.vue';
    // import myProductList from '../../../myProductList.json';
    // var product=myProductList;
    

    export default {
        
        data:function(){
            return{
                cat: 0,
                name:["jackets","trousers","tshirts","shoes"],
                // ProductList : product
                ProductList:[

                            {
                                jackets:[
                                    {title:"Jacket-A",price:"3150",imageurl:require("../../assets/jacket1.jpg")},
                                    {title:"Jacket-B",price:"2300",imageurl:require("../../assets/jacket2.jpg")},
                                    {title:"Jacket-C",price:"3500",imageurl:require("../../assets/jacket3.jpg")},
                                    {title:"Jacket-D",price:"2550",imageurl:require("../../assets/jacket4.jpg")},
                                    {title:"Jacket-E",price:"3200",imageurl:require("../../assets/jacket5.jpg")},
                                    {title:"Jacket-F",price:"3300",imageurl:require("../../assets/jacket6.jpg")},
                                    {title:"Jacket-G",price:"2750",imageurl:require("../../assets/jacket7.jpg")},
                                    {title:"Jacket-H",price:"3700",imageurl:require("../../assets/jacket8.jpg")}
                                ]
                            },
                            {
                                trousers:[
                                    {title:"Trousers-A",price:"1950",imageurl:require("../../assets/trousers1.jpg")},
                                    {title:"Trousers-B",price:"2250",imageurl:require("../../assets/trousers2.jpg")},
                                    {title:"Trousers-C",price:"2350",imageurl:require("../../assets/trousers3.jpg")},
                                    {title:"Trousers-D",price:"2550",imageurl:require("../../assets/trousers4.jpg")},
                                    {title:"Trousers-E",price:"2775",imageurl:require("../../assets/trousers5.jpg")},
                                    {title:"Trousers-F",price:"3000",imageurl:require("../../assets/trousers6.jpg")},
                                    {title:"Trousers-G",price:"2100",imageurl:require("../../assets/trousers7.jpg")},
                                    {title:"Trousers-H",price:"2700",imageurl:require("../../assets/trousers8.jpg")},
                                ]
                            },
                            {
                                tshirts:[
                                    {title:"T-shirt-A",price:"1250",imageurl:require("../../assets/tshirt1.jpg")},
                                    {title:"T-shirt-B",price:"1350",imageurl:require("../../assets/tshirt2.jpg")},
                                    {title:"T-shirt-C",price:"1450",imageurl:require("../../assets/tshirt3.jpg")},
                                    {title:"T-shirt-D",price:"1250",imageurl:require("../../assets/tshirt4.jpg")},
                                    {title:"T-shirt-E",price:"1150",imageurl:require("../../assets/tshirt5.jpg")},
                                    {title:"T-shirt-F",price:"1700",imageurl:require("../../assets/tshirt6.jpg")},
                                    {title:"T-shirt-G",price:"1650",imageurl:require("../../assets/tshirt7.jpg")},
                                    {title:"T-shirt-H",price:"1800",imageurl:require("../../assets/tshirt8.jpg")},
                                    
                                ]
                            },
                            {
                                shoes:[
                                    {title:"Shoes-A",price:"2750",imageurl:require("../../assets/shoes1.jpg")},
                                    {title:"Shoes-B",price:"3750",imageurl:require("../../assets/shoes2.jpg")},
                                    {title:"Shoes-C",price:"3550",imageurl:require("../../assets/shoes3.jpg")},
                                    {title:"Shoes-D",price:"4050",imageurl:require("../../assets/shoes4.jpg")},
                                    {title:"Shoes-E",price:"2550",imageurl:require("../../assets/shoes5.jpg")},
                                    {title:"Shoes-F",price:"3050",imageurl:require("../../assets/shoes6.jpg")},
                                    {title:"Shoes-G",price:"4750",imageurl:require("../../assets/shoes7.jpg")},
                                    {title:"Shoes-H",price:"4550",imageurl:require("../../assets/shoes8.jpg")},
                                ]
                         }
                         ] 

                
             }
        },
        components:{
            ProductMenu,
            ProductCard
        },

        created(){
            this.$eventBus.$on('get-category',(i)=>{
                this.cat=i;
            });
        }

    }
    
</script>

<style scoped>
    #product{
        min-height:800px;
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
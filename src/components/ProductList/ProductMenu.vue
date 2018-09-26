<template>
    <div id="product-menu">
        <ul>
            <li v-for="item in menuTitle" :key="item">{{item}}</li>
        </ul>
    </div>    
</template>

<script>
export default {
    data:function(){
        return{
            menuTitle:[
                "New Arrivals",
                "Most Popular",
                "Trending Now",
                "Discount Offer"
            ]
        }
    }
}
</script>

<style scoped>

    #product-menu{
        height: 40px;
        width: 100%;
        background:#05668d; 
        margin: 0;
        display: flex;
         align-items: center;
         /* position:sticky;
         top:50px; */

    }
    #product-menu ul{
        display: flex;
        list-style-type: none;
        margin:0;
        padding:0 0 0 10px;
        justify-content: flex-start;
        align-items: center;
       
        
    }

    ul li{
         list-style-type: none;
        padding: 10px 10px;
        border-right: solid 2px #7eb5cc;
        font-size: 14px;
    }

</style>


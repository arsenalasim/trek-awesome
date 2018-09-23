<template>
    <div id="product-menu">
        <ul style="margin-top:0;">
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
        height: 50px;
        width: 100%;
        background:#05668d; 
        margin: 0;

    }
    #product-menu ul{
        display: flex;
        list-style-type: disc;
        margin-top:0;
        
    }

</style>


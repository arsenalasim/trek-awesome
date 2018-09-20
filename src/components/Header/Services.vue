<template>
    <div id="service">
        <div class="servicelist">
            <img :src="delivery" alt="vehicle">
            <p>Low Shipping Rates</p>
        </div>

        <div class="servicelist">
            <img :src="exchange" alt="exchange">
            <p>Exchange and Returns</p>
        </div>

        <div class="servicelist">
            <img :src="reliable" alt="reliability">
            <p>Reliable Products</p>
        </div>


    </div>
</template>

<script>
import delivery2 from '../../assets/delivery2.png';
import return5 from '../../assets/return5.png';
import reliable2 from '../../assets/reliable2.png';

export default {
    data: function(){
        return{
            delivery:delivery2,
            exchange:return5,
            reliable:reliable2
        }
    }
    
}
</script>

<style scoped>
    #service{
        height: 50px;
        width: 100%;
        background-color: #02c39a;
        display: flex;
        justify-content: space-around;
    }

    .servicelist{
        display:flex;
        justify-content:space-around;
        color: #05668d;


    }

    img{
        height: 50px;
        width: 60px;
        padding: 0 15px;
    }

</style>



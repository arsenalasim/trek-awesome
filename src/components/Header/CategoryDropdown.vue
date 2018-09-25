<template>
    <div id="dropdown">
        <ul>
            <li v-for="(item,index) in dropdownItems" :key="item" v-on:click="sendCategory(index); scrollWindow();">{{item}}</li>
        </ul>

    </div>
    
</template>

<script>
export default {
    data: function(){
        return{
            dropdownItems:[
                "Jackets",
                "Trousers",
                "T-shirts",
                "Shoes"

            ]
        }
    },
    methods:{
        sendCategory:function(i){
            this.$eventBus.$emit('get-category',i);
        },

        scrollWindow:function(){
           
            window.scrollTo(0,550);
        }
    }
    
}
</script>

<style scoped>

    ul li{
        list-style-type: none;
         margin:0;
        padding: 15px 15px;
        font-weight: bold;
    }
    ul{
        margin:0;
        padding: 10px 20px;
    }

    ul li:hover{
        background:#6fb6d4;
        opacity: 0.9;
        color:white;
        transform: scale(1.2);
        cursor: pointer;
    }

</style>



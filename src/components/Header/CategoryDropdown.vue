<template>
    <div id="dropdown">
        <ul>
            <li v-for="item in dropdownItems" :key="item">{{item}}</li>
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
    }
    
}
</script>

<style scoped>

    ul li{
        list-style-type: none;
         margin:0;
        padding: 15px 15px;
    }
    ul{
        margin:0;
        padding: 10px 20px;
    }

    ul li:hover{
        background:#02c39a;
        opacity: 0.9;
        color:white;
        transform: scale(1.2);
        cursor: pointer;
    }

</style>



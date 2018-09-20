<template>
    <div id = "social-media">
         <div id="media-icons">
            <img src="../../assets/facebookicon2.png" alt="facebook">
            <img src="../../assets/twittericon.png" alt="twitter">
            <img src="../../assets/googleicon.png" alt="google">
            <img src="../../assets/youtubeicon.png" alt="youtube">
        </div>
    </div>
    
</template>

<script>
export default {
    
}
</script>

<style scoped>

     #media-icons{
        position: absolute;
        height: 50px;
        width: 50px;
        top:50px;
        right: 0px;
        
        
    }

    #media-icons img{
     
        opacity: 0.7;
    }
    #media-icons img:hover{
        cursor: pointer;
        opacity: 1;
        transform: scale(1.2);
    }

</style>



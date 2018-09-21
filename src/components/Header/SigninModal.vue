<template>
    <div id="signin" class="modal">
        <span onclick="document.getElementById('signin').style.display='none'" class="close" 
         title="Close Modal">&times;</span>

         <!-- modal content -->
         <form class="modal-content animate" action="#">
             <div class="avatar">
                 <img src="../../assets/avatar1.png" alt="user avatar" style="height:100px;width:100px;">

             </div>

             <div class="container">
                 <label for="username">Username : </label>
                 <input type="text" placeholder="Enter username" name="username" required>

                 <label for="password">Password : </label>
                 <input type="text" placeholder="Enter password" name="password" required>

                 <button type="submit">Submit</button>
                 <label>
                     <input type="checkbox" checked="checked" name="remember">Remember me
                 </label>

             </div>

             <div class="container">
                 <button type="button" onclick="document.getElementById('signin').style.display='none'"
                 class="cancelbtn">Cancel</button>

                 <span class="psw">Forgot <a href="#">Password ?</a></span>

             </div>


         </form>


    </div>
    
</template>

<script>
export default {
    
}
</script>

<style scoped>
    body {font-family: Arial, Helvetica, sans-serif;}

    /* Full-width input fields */
    input[type=text], input[type=password] {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }

    /* Set a style for all buttons */
    button {
        background-color: #4CAF50;
        color: white;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        cursor: pointer;
        width: 100%;
    }

    button:hover {
        opacity: 0.8;
    }

/* Extra styles for the cancel button */
    .cancelbtn {
        width: auto;
        padding: 10px 18px;
        background-color: #f44336;
        
    }

        /* Center the image and position the close button */
    .imgcontainer {
        text-align: center;
        margin: 24px 0 12px 0;
        position: relative;
    }

    .avatar img{
        width: 40%;
        border-radius: 50%;
        padding-top: 15px;
    }

    .container {
        padding: 16px;
        text-align: left;
    }

    span.psw {
        float: right;
        padding-top: 16px;
    }

    .modal{
        display: none;
        position:fixed;
        z-index: 1;
        top:0;
        left:0;
        width:100%;
        height:100%;
        overflow: auto;
        background-color: rgba(0,0,0,0.4);
        padding-top: 40px;
    }

    .modal-content{
        background-color: #fefefe;
        margin:5% auto 15% auto;
        border: 1px solid #888;
        width: 80%;
        height: auto;
    }

    /* close button */
    .close{
        position: absolute;
        right:35px;
        top:15px;
        color:rgb(206, 62, 62);
        font-size: 55px;
        font-weight: bold;
    }

    .close:hover, .close:focus{
        color: red;
        cursor: pointer;
    }

    .animate{
        animation: animatezoom 0.6s;
    }

    @keyframes animatezoom {
        from{transform : scale(0)}
        to{transform: scale(1)}
        
    }

</style>



<template>
    <div id="cart" class="modal" :style="{display:displayModal}">
        <span @click="$emit('close-cart')" class="close" 
         title="Close Modal">&times;</span>

         <!-- modal content -->
         <form class="modal-content animate" action="#">
             <div class="avatar">
                 <img src="../../assets/cart4.png" alt="user avatar" style="height:100px;width:100px;">

             </div>

             <div class="container">
                 <table style="width:80%;">
                     <tr>
                         <th style="width:40px;">S.N.</th>
                         <th colspan="2">Items</th>
                         <th>Quantity</th>
                         <th>Price</th>
                         <th>Total</th>
                         <th></th>
                     </tr>
                     <tr v-for="(item,i) in selectedItems" :key="i">
                         <td style="width:40px;">{{i+1}}</td>
                         <td><img :src='item.imageurl' alt="image" class="product-image"></td>
                         <td>{{item.name}}</td>
                         <td class="align-right"><input type="number" v-model="item.quantity" class="quantity"></td>
                         <td class="align-right">{{item.price}}</td>
                         <td class="align-right">{{item.price * item.quantity}}</td>
                         <td class="align-right"><button  class="cancelbtn" @click="removeFromCart(i,item)">Remove</button></td>
                     </tr>
                     <tr>
                         <td colspan="4" class="remove-border"></td>
                         <td colspan="1">Total : </td>
                         <td colspan="2">{{total}}</td>              
                     </tr>

                     <tr>
                         <td colspan="4" class="remove-border"> 13% VAT is imposed as per the recent govt act.</td>
                         <td colspan="1">VAT : </td>
                         <td colspan="2">{{vat}}</td>              
                     </tr>

                     <tr>
                         <td colspan="4" class="remove-border"></td>
                         <td colspan="1">Grand-Total : </td>
                         <td colspan="2">{{grandTotal}}  &nbsp;&nbsp;Rupees only.</td>              
                     </tr>
                     

                 </table>
                

             </div>

             <div class="container">
                 <button type="button" @click="$emit('close-cart')" class="cancelbtn">Cancel</button>

                <button type="button" onclick="#" class="chkout">Checkout</button>

             </div>


         </form>


    </div>
    
</template>

<script>
export default {
    data:function(){
        return{
            displayValue:"none",
            selectedItems:[
                // {name:"Jacket-A",quantity:2,price:3250,imageurl:require("../../assets/jacket1.jpg")},
                // {name:"Jacket-C",quantity:1,price:2250,imageurl:require("../../assets/jacket3.jpg")},
                // {name:"Shoes-D",quantity:1,price:3050,imageurl:require("../../assets/shoes4.jpg")},
                // {name:"T-shirt-B",quantity:3,price:1250,imageurl:require("../../assets/tshirt2.jpg")},
                // {name:"Trousers-G",quantity:2,price:2550,imageurl:require("../../assets/trousers7.jpg")}
            ],
            total:0,
            vat:0,
            grandTotal:0
        }
    },
    props:[
        'displayModal'
    ],
    created: function () {
      this.$eventBus.$on('add-to-cart', this.pushToSelectedItems);
      this.$eventBus.$on('calculate-total',this.calculateTotal);
      
  },
  methods: {
    pushToSelectedItems:function (itemObject) {
        this.selectedItems.push(itemObject);
    },

    calculateTotal:function(){
        var len=this.selectedItems.length;
        var tot=0;
        // console.log(this.selectedItems[0]);
        // console.log(this.selectedItems[0].price);
        // console.log(parseInt(this.selectedItems[0].price)*this.selectedItems[0].quantity);
        for(var i=0;i<len;i++){
            tot+=parseInt(this.selectedItems[i].price)*this.selectedItems[i].quantity;
        }
        this.total=tot;
        // console.log(this.total);
        this.vat=(0.13*this.total);
        // console.log(this.vat);
        this.grandTotal=(this.total+this.vat);
        
       
    },
    removeFromCart:function(i,item){
        this.selectedItems.splice(i,1);
        this.calculateTotal();
        console.log("removed this item from the cart: " +item.myObj.description);
        
        this.$eventBus.$emit("remove-from-cart",item.myObj.cate,item.myObj.index);
        
    }
  }
}
</script>

<style scoped>
    body {font-family: Arial, Helvetica, sans-serif;}

    table, th, td{
        border: 1px solid lightskyblue;
        border-collapse: collapse;
    }

    table{
        margin: 5px auto;
    }

    th,td{
        padding:10px;
        width:16%;
    }

    .align-right{
        text-align: right;
    }

    .product-image{
        height: 100px;
        width: 100px;
    }

    .remove-border{
        border-style: none;
    }

    /* table tr:nth-child(even) .align-right{
        background-color: #eeeeee;
    }

    #quantity tr:nth-child(odd) {
         background:#eeeeee;
    } */

    .quantity{
        height: 100px;
        box-sizing: border-box;
        width: 100%;
        margin: 0;
        padding:0;
        border: none;
       
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
    /* .imgcontainer {
        text-align: center;
        margin: 24px 0 12px 0;
        position: relative;
    } */

    .avatar img{
        width: 40%;
        border-radius: 50%;
        padding-top: 15px;
    }

    .container {
        padding: 16px;
        text-align: left;
    }

    button.chkout {
        float: right;
        padding:10px 18px;
        display:block;
        width:auto;
        
    }

    .modal{
        /* display: none; */
        position:fixed;
        z-index: 10;
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
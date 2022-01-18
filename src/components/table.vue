<template>
      <table class="table">
        <thead class="border-0">
            <tr class="header border-0">
                <th>  </th>
                <th> نام درس </th>
                <th> ضریب </th>
                <th> نمره </th>
                <th>  </th>
            </tr>
            <tr>
                <td></td>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(pro,index) in products" class="border-0" :key="pro.id">
                <counter :index="index" />
                <name />
                <td> <input type="number" v-model="pro.factor" class="form-control"> </td>
                <td> <input type="number" v-model="pro.score" class="form-control"> </td>
                <td> <button class="float-right btn-del" @click="del(index)"> <i class="fa fa-close close"></i> </button> </td>
            </tr>
            <tr> 
                <td> <addbtn @click="addtocart"  /> </td>
            </tr>
        </tbody>
    </table>
       <avg :subtotal="subtotal" />
</template>

<script>
import addbtn from './addbtn.vue'
import avg from './avg.vue'
import counter from './counter.vue'
import name from './name.vue'
export default {
name:'mytable',
components:{addbtn,avg,counter,name},
data(){
    return{
        products:[
          { id:1 , name:'ریاضی' , score:20 , factor:2}
        ],
        product:{
            id:'',
            name:'',
            score:'',
            factor:'',
            temp:''
        },

    }
},
    methods:{
        addtocart(){
        var id = this.product.id
        var name = this.product.name
        var score = this.product.score
        var factor = this.product.factor

        this.products.push({ id:id , name:name , score:score , factor:factor })

            } ,
        del(index){
            this.products.splice(index,1)
        }

        },
        computed:{
            sub: function(){
              return this.products.reduce(function(total,item){
              return (total + item.score * item.factor)
             },0)
      },
            num :function(){
              return this.products.reduce(function(total,item){
                  return total + item.factor
              },0)
            },
        subtotal(){
            return this.sub / this.num
        },

    },



}
</script>

<style>
input{
    padding: 10px 12px;
    border-radius: 5px;
    border: none;
    outline: none;
}
.bdy{
    background-color: #101820;
    color: #f2aa4c !important;
    border-radius: 180px 10px 10px 50px;
}
.header{
    color: #f2aa4c !important;
    font-size: larger;
    text-align: center;
    font-weight: 800 !important;
}
.header th{
    padding: 15px;
}
.table td, .table th {
    border: none !important;
}
.btn-add{
    background-color: #f2aa4c !important;
    border-radius: 27% !important;
    padding: 10px;
    border: none;
    outline: none;
    margin-left: -27px;
    margin-top: 20px;
    cursor: pointer;
    transition: all ease .5s;
    background: rgba(255, 255, 255, .1);}
.btn-del{
    cursor: pointer;
    transition: all ease .5s;
    color: red !important;
    background: transparent;
    border:none;
    outline: none;
}
.close{
    font-size: 30px;
}
.btn-del:hover{
    color: white !important;

}
.btn-record{
    background-color: #f2aa4c !important;
    border: none !important;
    color: #101820 !important;
    font-size: 16px !important;
    font-weight: bold !important;
    border-radius: 0 8px 8px 0 !important;
    padding: 6px 10px !important;
    font-family: IS;
    outline: none;
    padding-bottom: 6px !important;
}
.input-record{
    border-radius: 8px 0 0 8px !important;
}
.title{
    width: 250px;
    height: 15px;
    background-color: #f2aa4c !important;
    color: #101820 !important;
    text-align: right;
    padding: 20px 60px;
    border-radius: 100px 10px 10px 50px;
    margin-bottom: 60px;
}
.title h3{
    font-size: 26px;
    margin: -8px 6px;
}
.container{
    max-width: 1000px;
    text-align: center;
    direction: rtl;
    margin: 0 auto;
}
table{
    margin: auto;
}
    .mb-3{
        padding-bottom:20px
    }
    .mt-5{
        padding-top: 25px;
    }
 
</style>
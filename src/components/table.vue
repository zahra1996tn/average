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

</style>
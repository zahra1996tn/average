<template>
          <div class="container bdy">
            <div class="row mt-5">
                <div class="col-md-12">
                    <div class="title mt-4">
                        <h3><i class="fa fa-calculator"></i> محاسبه معدل </h3>
                    </div>
                    <table class="table">
                        <thead class="border-0">
                            <tr class="header border-0">
                                <th> شماره </th>
                                <th> نام درس </th>
                                <th> ضریب </th>
                                <th> نمره </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="pro in products" class="border-0" :key="pro.id">
                                <td> <input type="number" v-model="pro.id" class="form-control"> </td>
                                <td> <input type="text" v-model="pro.name" class="form-control"> </td>
                                <td> <input type="number" v-model="pro.factor" class="form-control"> </td>
                                <td> <input type="number" v-model="pro.score" class="form-control"> </td>
                            </tr>
                            <tr>
                                <td class="td-btn"> <button class="btn-add float-right" @click="addtocart"> + </button> </td>
                            </tr>
                        </tbody>
                    </table>
                    <div class="row border-top box-btn mb-3 d-flex justify-content-center mt-5">
                        <div class="col-md-4">
                            <form>
                                <div class="input-group mt-5 mb-3">
                                    <button class="btn-record" @click="subtotal"> محاسبه </button>
                                    <input class="input-record" :value="subtotal">
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>

</template>

<script>
export default {
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
/* body{
    font-family: IS;
} */
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
.table td, .table th {
    border: none !important;
}
.btn-add{
    background-color: #f2aa4c !important;
    border-radius: 27% !important;
    padding: 10px;
    border: none;
    outline: none;
    margin-left: 149px;
    margin-top: 20px;
    cursor: pointer;
}
.btn-record{
    background-color: #f2aa4c !important;
    border: none !important;
    color: #101820 !important;
    font-size: 16px !important;
    font-weight: bold !important;
    border-radius: 0 8px 8px 0 !important;
    padding: 8px 10px;
    font-family: IS;
    cursor:pointer;
    outline: none;
    padding-bottom: 10px;
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
 /* @font-face{
    font-family: IS;
    font-style: normal;
    src: url("public/font/IRAN Sans Regular (mmrostami.blog.ir).ttf");
    }  */
    .mb-3{
        padding-bottom:20px
    }
    .mt-5{
        padding-top: 25px;
    }
</style>
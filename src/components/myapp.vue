<template>
    <div class="container bdy">
    <div class="row mt-5 content">
        <div class="col-md-12">
    <div class="title mt-4">
        <h3><i class="fa fa-calculator"></i> محاسبه معدل </h3>
    </div>

<!-- جدول -->   
<mytable />

    <div class="row border-top box-btn mb-3 d-flex justify-content-center mt-5">
        <div class="col-md-4">
            <form>
                <div class="input-group mt-5 mb-3">
                    <!-- <input class="input-record" :value="subtotal"> -->
                </div>
            </form>
        </div>
    </div>
        </div>
    </div>
</div>

</template>

<script>
import mytable from './table.vue'
export default {
  components: { mytable},
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
}
</script>

<style>

</style>
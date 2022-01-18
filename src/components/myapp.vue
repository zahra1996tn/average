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
body{
    font-family: IS;
}
input{
    padding: 10px 12px;
    border-radius: 5px;
    border: none;
    outline: none;
}
.header{
    /* color: #f2aa4c !important; */
    font-size: larger;
    text-align: center;
    font-weight: 800 !important;
}
.table td, .table th {
    border: none !important;
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
    margin-top: -90px;
}
.title h3{
    font-size: 26px;
    margin: -8px 6px;
}
.container{
    text-align: center;
    direction: rtl;
    margin: 0 auto;
    /**/ 
     position: relative;
    max-width: 1000px;
    margin: 30px;
    margin-top: 120px !important;
    box-shadow: 20px 20px 50px rgba(0, 0, 0, .5);
    border-radius: 15px;
    background: rgba(255, 255, 255, .1);
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    border-top: 1px solid rgba(255, 255, 255, .5);
    border-left: 1px solid rgba(255, 255, 255, .5);
    backdrop-filter: blur(5px);
    color: rgba(255, 255, 255, .5) !important;
    width: 1100px;
}
table{
    margin: auto;
}
 @font-face{
    font-family: IS;
    font-style: normal;
    src: url("/font/IRAN Sans Regular (mmrostami.blog.ir).ttf");
    } 
    .mb-3{
        padding-bottom:20px
    }
    .mt-5{
        padding-top: 25px;
    }
    .content{
    padding: 20px;
    text-align: center;
    transition: .5s;
    transform: translateY(100px);

    }
</style>
<template>
   <td> <button class="counter"> {{index+1}} </button> </td>
</template>

<script>
export default {
    name:'item',
    props:['index']
}
</script>

<style>
   .counter{
    color:#f2aa4c ;
    border: none;
    outline: none;
    float: left;
    background: transparent;
    font-size: 18px;
}
</style>
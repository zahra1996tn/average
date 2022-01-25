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
</style>
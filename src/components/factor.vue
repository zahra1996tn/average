<template>
     <!-- <td> <input type="number" v-model="profactor" class="form-control"> </td> -->
    <td> 
       <input type="number"
        :value="modelValue" v-on="$Listener" @input="$emit('update:modelValue',$event.target.value)">
    </td>
</template>

<script>
export default {
    props:{
        modelValue:Number
    }
}
</script>

<style>

</style>
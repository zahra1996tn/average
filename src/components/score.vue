<template>
    <td> 
       <input type="number"
        :value="modelValue" @input="$emit('update:modelValue',$event.target.value)">
    </td>
</template>

<script>
export default {
props:['modelValue']
}
</script>

<style>

</style>
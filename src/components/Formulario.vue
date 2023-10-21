<script setup>

const props = defineProps(["numero1", "numero2", "operacao"])

</script>

<template>
    <form class="row p-5 d-flex gap-5 justify-content-center">
        <input @keyup="props.numero1" type="number" class="text-center col-sm-12 col-lg-5">
        <select @change="props.operacao" class="col-sm-12 col-lg">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">X</option>
            <option value="/">/</option>
        </select>
        <input @keyup="props.numero2" type="number" class="text-center col-sm-12 col-lg-5">
    </form>
</template>

<style scoped>

input{
    -moz-appearance: textfield;
    appearance: textfield;
    outline: none;
    background-color: transparent;
}
input[type=number]::-webkit-inner-spin-button { 
    -webkit-appearance: none;
}

select{
    text-align: center;
    background-color: transparent;
    outline: none;
    padding: 0 10px 0 13px;
    -webkit-appearance: none;
    -moz-appearance: none;  
    appearance: none;
}


</style>
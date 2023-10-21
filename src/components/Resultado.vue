<script setup>

const props = defineProps(["resultado"])

</script>

<template>
    <div class="display rounded-3 py-5 d-flex gap-5 justify-content-center align-items-center">
        <h2>Resultado:</h2>
        <p>{{ props.resultado }}</p>
    </div>
</template>

<style scoped>

.display{
    background-color: black;
    color: white;
}
</style>
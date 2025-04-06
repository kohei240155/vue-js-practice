<script setup>
defineProps({
    text: String,
});
const dataTest = "これはデータです！"
</script>

<template>
    <p>{{ dataTest }}</p>
    <p v-text="text"></p>
</template>
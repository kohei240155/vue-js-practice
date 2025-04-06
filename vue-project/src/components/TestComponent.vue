<script setup>
defineProps({
    text: String,
});
const dataTest = "これはデータです！"
const imageUrl = "/sample.png"
</script>

<template>
    <!-- テキストバインディング(マスタッシュ構文) -->
    <p>{{ dataTest }}</p>
    <!-- テキストバインディング(通常) -->
    <p v-text="text"></p>
    <!-- 属性バインディング -->
    <img v-bind:src="imageUrl" />
    <!-- 属性バインディング(省略版) -->
    <img :src="imageUrl"/>
</template>
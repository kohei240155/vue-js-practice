<script setup>
defineProps({
    text: String,
});
const dataTest = "これはデータです！"
const imageUrl = "/sample.png"
function myMethod() {
    console.log("メソッド実行")
}
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
    <!-- イベントバインディング -->
    <button v-on:click="myMethod">メソッド実行</button>
    <!-- イベントバインディング(省略版) -->
    <button @click="myMethod">メソッド実行</button>
</template>
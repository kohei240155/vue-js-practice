<script setup>
import { ref } from 'vue';

defineProps({
    text: String,
});
const dataTest = "これはデータです！"
const imageUrl = "/sample.png"
function myMethod() {
    console.log("メソッド実行")
}
const name = ref("")
const fruitsList = [
    {id: 1, name: "りんご"},
    {id: 2, name: "いちご"},
    {id: 3, name: "バナナ"}
    ]
const number = 5
const count = ref(0)
const increment = () => {
    count.value++
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
    <!-- 双方向バインディング -->
    <div>
        <label for="name">名前：</label>
        <input type="text" id="name" v-model="name">
        <p>入力された名前：{{ name }}</p>
    </div>
    <!-- v-for -->
     <ul>
        <li v-for="fruit in fruitsList" :key="fruit.id">{{ fruit.name }}</li>
     </ul>
    <!-- v-if -->
    <div>
        <p v-if="number < 10">数字は10より小さいです(v-if)</p>
        <p v-else>数字は10より大きいです(v-if)</p>
    </div>
    <!-- v-show -->
    <div>
        <p v-show="number < 10">数字は10より小さいです(v-show)</p>
    </div>
    <!-- Setup -->
     <p>{{ count }}</p>
     <button v-on:click="increment">カウントアップ</button>
</template>
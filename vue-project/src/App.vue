<script setup>
import { ref } from 'vue';
import TestComponent from './components/TestComponent.vue';

const receivedMessage = ref("")
function handleMessage(message) {
  receivedMessage.value = message;
}
</script>

<template>
    <TestComponent text="propsを試してみた!" @message="handleMessage"/>
    <p>{{ receivedMessage }}</p>
</template>

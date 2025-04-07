<script setup>
import { statuses } from '@/const/statuses';
import { ref } from 'vue';

const input = ref("")
const inputDate = ref("")

function onSubmitForm() {
    console.log(input.value)

    const items = JSON.parse(localStorage.getItem("items")) || [];

    const newItem = {
        id: items.length,
        content: input.value,
        limit: inputDate.value,
        state: statuses.NOT_START,
        onEdit: false,
    }

    items.push(newItem);

    localStorage.setItem("items", JSON.stringify(items));
}
</script>

<template>
    <div>
        <form v-on:submit="onSubmitForm">
            <label>やること<input type="text" v-model="input"/></label>
            <label>期限<input type="date" v-model="inputDate"/></label>
            <input type="submit" value="登録！">
        </form>
    </div>
</template>
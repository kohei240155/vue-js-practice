<script setup>
import { statuses } from '@/const/statuses';
import { ref } from 'vue';

const input = ref("");
const inputDate = ref("");
const isErrMsg = ref(false);

function onSubmitForm() {
    if (input.value == "" || inputDate.value == "") {
        isErrMsg.value = true;
        event.preventDefault();
        return;
    }

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
        <p v-if="isErrMsg">タスク・期限を両方入力してください。</p>
        <form v-on:submit="onSubmitForm">
            <label>やること<input type="text" v-model="input"/></label>
            <label>期限<input type="date" v-model="inputDate"/></label>
            <input type="submit" value="登録！">
        </form>
    </div>
</template>
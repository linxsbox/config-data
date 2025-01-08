<script setup>
import { ref } from 'vue';
// 支持工具库 @linxs/toolkit
import { clipboard } from "@linxs/toolkit";

const msg = ref('hello');
const tips = ref('')
const handleCopy = () => {
    clipboard({
        data: msg.value,
        success: (msg) => {
            tips.value = msg;
        },
        error: (msg) => {
            tips.value = msg;
        },
    });
}
</script>

<template>
    <div class="demo1">{{ msg }}</div>
    <input v-model="msg">
    <button type="button" @click="handleCopy">复制</button>
    <div>{{ tips }}</div>
</template>

<style scoped>
.demo1 {
    color: red;
}
</style>
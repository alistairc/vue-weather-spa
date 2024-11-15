<script setup lang="ts">
import { ref } from 'vue'

const viewModel = {
    count: ref(0),
    message: ref(""),
    up(): void {
        if (this.count.value == 10) {
            this.message.value = "Can't go any higher!"
            return;
        }
        this.message.value = ""

        this.count.value++;
    },
    down(): void {
        if (this.count.value == 0) {
            this.message.value = "Can't go any lower!"
            return;
        }
        this.message.value = ""
        this.count.value--;
    }
}
</script>

<template>
    <button @click="viewModel.up">Up</button>
    <button @click="viewModel.down">Down</button>
    Count is: {{ viewModel.count }}
    <div>{{ viewModel.message }}</div>
</template>

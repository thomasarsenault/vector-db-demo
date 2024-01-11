<script setup lang="ts">
import { ref } from 'vue'
const text = ref('')

const emit = defineEmits(['send'])

const handleEnter = () => {
    emit('send', text.value)
    text.value = ''
}

</script>

<template>
    <input
        type="text"
        placeholder="Type a message..."
        class="chat-input"
        :value="text"
        @input="e => text = e.target.value"
        @keyup.enter="handleEnter"
    />
</template>

<style scoped lang="scss">
.chat-input {
    padding: 1rem;
    border-radius: 12px;
    margin-top: 1rem;
    background-color: rgb(37, 37, 37);
    color: white;
    border: none;
    font-size: 20px;
}
</style>

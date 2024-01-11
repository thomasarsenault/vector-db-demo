<script setup lang="ts">
//define props, where role is a string and content is a string
defineProps<{
    chat: {
        role: string
        content: string
    }}>()

</script>

<template>
    <div class="wrapper">
        <div class="bubble user" v-if="chat.role === 'user'">
            <img src="https://cdn-icons-png.flaticon.com/512/6134/6134346.png" />
            <div class="bubble-content">
                {{ chat.content }}
            </div>
        </div>
        <div class="bubble system" v-else>
            <img src="https://cdn-icons-png.flaticon.com/512/6134/6134346.png" />
            <div class="bubble-content">
                {{ chat.content }}
            </div>
        </div>
    </div>

</template>

<style scoped lang="scss">
.wrapper {
    display: flex;
    flex-direction: column;
}
.bubble {
    display: flex;
    gap: 1rem;
    margin: 0.5rem;
    border-radius: 12px;
    color: white;
    padding: 1rem;

    img {
        width: 35px;
        height: 35px;
        border-radius: 50%;
    }

    &.system {
        background-color: rgb(65, 65, 65);
    }
}
</style>

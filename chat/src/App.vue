<script setup lang="ts">
import ChatInput from './components/ChatInput.vue'
import ChatBubble from './components/ChatBubble.vue';
import { ref } from 'vue'

const chats: any = ref([{
  role: "system",
  content: "Welcome to Vector DB Chat!"
}]);

const sendMessage = (msg) => {
  chats.value.push({role: "user", "content": msg});
  console.log(chats.value);
}
</script>

<template>
    <header>Large Language Models - Vector Databases</header>
    <main>
      <div class="chat">
        <ChatBubble v-for="chat in chats" :key="chat" :chat="chat"/>
      </div>
      <ChatInput @send="sendMessage"/>
    </main>
</template>

<style scoped lang="scss">
main {
  height: 100%;
  padding: 1rem 0;
  display: flex;
  flex-direction: column;
}
.chat {
  height: 100%;
  border-radius: 12px;
  background-color: rgb(37, 37, 37);
  display: flex;
  flex-direction: column;
}
</style>

<!-- src/App.vue -->
<template>
  <Navbar />
  <ChatBot />
</template>

<script>
import ChatBot from './views/ChatBot.vue';
import Navbar from './components/Navbar.vue';

export default {
  // name: 'App',
  components: {
    ChatBot,
    Navbar,
  },
};
</script>

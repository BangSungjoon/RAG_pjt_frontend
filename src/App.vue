<!-- src/App.vue -->
<template>
  <Navbar />
  <RouterView />
</template>

<script>
import ChatBot from './views/ChatBot.vue';
import Navbar from './components/Navbar.vue';
import { RouterLink, RouterView } from 'vue-router'

export default {
  name: 'App',
  components: {
    ChatBot,
    Navbar,
  },
};
</script>

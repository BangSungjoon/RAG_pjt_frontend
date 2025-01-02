<!-- src/views/ChatBot.vue -->
<template>
    <div id="bot">
      <h1>AI 상담원</h1>
  
      <!-- 메시지 목록 -->
      <ChatBox :messages="messages"/>
  
      <!-- 메시지 입력란 -->
      <InputBox
        :userMessage="userMessage"
        @update:userMessage="userMessage = $event"
        @send-message="sendMessage"
      />
    </div>
  </template>
  
  <script>
  // 컴포넌트를 상단에서 import
  import { ref } from 'vue';
  import axios from 'axios';
  import ChatBox from '../components/ChatBox.vue';  // ChatBox 컴포넌트 import
  import InputBox from '../components/InputBox.vue'; // InputBox 컴포넌트 import
  
  export default {
    name: 'ChatBot',
    components: {
      ChatBox,  // 자식 컴포넌트로 등록
      InputBox, // 자식 컴포넌트로 등록
    },
    setup() {
      const userMessage = ref('');
      const messages = ref([]);
  
      // 메시지 전송 함수
      const sendMessage = async () => {
        if (userMessage.value.trim() === '') return; // 빈 메시지 방지
  
        // 사용자의 메시지를 messages 배열에 추가
        messages.value.push({ role: 'user', content: userMessage.value });
  
        // 백엔드로 메시지 전송
        try {
          const response = await axios.post('http://localhost:8000/chat', {
            messages: messages.value,
          });
  
          // 서버에서 받은 답변을 messages 배열에 추가
          messages.value.push({ role: 'assistant', content: response.data.reply });
        } catch (error) {
          console.error('Error sending message:', error);
        } finally {
          // 입력 필드 초기화
          userMessage.value = '';
        }
      };
  
      return {
        userMessage,
        messages,
        sendMessage,
      };
    },
  };
  </script>
  
  <style scoped>
  #bot {
    font-family: 'Noto Sans KR', sans-serif;
    text-align: center;
    margin-top: 25px;
  }
  h1 {
    margin-bottom: 25px;
  }
  </style>
  
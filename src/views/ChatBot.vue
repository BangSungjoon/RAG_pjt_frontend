<template>
  <div id="bot">
    <h1>AI 상담원</h1>

    <!-- 메시지 목록 -->
    <ChatBox :messages="messages">
      <!-- 로딩 중 메시지 슬롯 -->
      <template #footer>
        <div v-if="isLoading" class="loading-message">
          답변을 불러오는 중...
        </div>
      </template>
    </ChatBox>

    <!-- 메시지 입력란 -->
    <InputBox
      :userMessage="userMessage"
      @update:userMessage="userMessage = $event"
      @send-message="sendMessage"
    />
  </div>
</template>

<script>
import { ref } from 'vue';
import axios from 'axios';
import ChatBox from '../components/ChatBox.vue';
import InputBox from '../components/InputBox.vue';

export default {
  name: 'ChatBot',
  components: {
    ChatBox,
    InputBox,
  },
  setup() {
    const userMessage = ref('');
    const messages = ref([]);
    const isLoading = ref(false); // 로딩 상태를 관리하는 변수

    // 메시지 전송 함수
    const sendMessage = async () => {
      if (userMessage.value.trim() === '') return;

      // 사용자의 메시지를 messages 배열에 추가
      messages.value.push({ role: 'user', content: userMessage.value });

      // 입력 필드 초기화
      userMessage.value = '';
      
      // 로딩 상태 시작
      isLoading.value = true;

      // 백엔드로 메시지 전송
      try {
        const response = await axios.post('https://backend-nameless-silence-5442.fly.dev/chat', {
          messages: messages.value,
        });

        // 서버에서 받은 답변을 messages 배열에 추가
        messages.value.push({ role: 'assistant', content: response.data.reply });
      } catch (error) {
        console.error('Error sending message:', error);
        messages.value.push({ role: 'assistant', content: '오류가 발생했습니다. 다시 시도해 주세요.' });
      } finally {
        // 로딩 상태 종료
        isLoading.value = false;
      }
    };

    return {
      userMessage,
      messages,
      isLoading,
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
.loading-message {
  margin: 15px 0;
  font-style: italic;
  color: gray;
}
</style>

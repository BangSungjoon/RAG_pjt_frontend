<!-- src/components/ChatBox.vue -->
<template>
    <div class="chat-box">
      <div v-for="(msg, index) in messages" :key="index" :class="['message', msg.role]">
        <span>{{ msg.content }}</span>
      </div>
      <slot name="footer"></slot>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ChatBox',
    props: {
      messages: Array,
    },
  };
  </script>
  
  <style scoped>
  .chat-box {
    max-width: 700px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    /* min-height: 400px;
    max-height: 500px;  */
    width: 80%;
    height: 65vh;
    overflow-y: auto; /* 대화 내용이 길어지면 스크롤이 생김 */
    background-color: #f9f9f9;
    display: flex;
    flex-direction: column;
    gap: 10px; /* 메시지 간 간격 */
  }
  
  .message {
    padding: 10px;
    border-radius: 5px;
    max-width: 80%;
    word-break: break-word;
    display: inline-block;
    white-space: pre-wrap;
  }
  
  .user {
    background-color: #e1f5fe;
    align-self: flex-end; /* 유저 메시지는 오른쪽 정렬 */
    text-align: right;
  }
  
  .assistant {
    background-color: #FFF3B0; /* 연한 노란색 */
    align-self: flex-start; /* 어시스턴트 메시지는 왼쪽 정렬 */
    text-align: left;
  }
  </style>
  
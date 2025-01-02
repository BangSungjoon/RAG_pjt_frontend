<!-- src/components/InputBox.vue -->
<template>
    <div class="input-box">
      <input
        :value="userMessage"
        @input="updateMessage"
        @keyup.enter="sendMessage"
        placeholder="메시지를 입력하세요..."
      />
      <button @click="sendMessage">전송</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'InputBox',
    props: {
      userMessage: String, // 부모로부터 전달받은 값
    },
    emits: ['update:userMessage', 'send-message'], // 이벤트를 통해 값을 부모로 전달
    methods: {
      updateMessage(event) {
        this.$emit('update:userMessage', event.target.value); // 부모에 값 전달
      },
      sendMessage() {
        this.$emit('send-message'); // 메시지 전송
      }
    }
  };
  </script>
  
  <style scoped>
  .input-box {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
  
  .input-box input {
    padding: 10px;
    width: 300px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
  
  .input-box button {
    padding: 10px;
    margin-left: 10px;
    background-color: #00796b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .input-box button:hover {
    background-color: #004d40;
  }
  </style>
  
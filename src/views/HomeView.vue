<template>
    <div id="home">
      <!-- 헤더 -->
      <header class="home-header">
        <h1>AI 상담 서비스</h1>
        <p>당신의 질문에 빠르고 정확하게 답변해드리는 AI 상담 서비스</p>
      </header>
  
      <!-- 서비스 소개 -->
      <section class="intro">
        <h2>서비스 소개</h2>
        <p>
          우리의 AI 상담 서비스는 다양한 질문에 대해 빠르게 답변하고,
          사용자의 요구에 맞는 맞춤형 정보를 제공합니다. 기술을 활용하여
          실시간으로 상담을 진행하며, 필요한 모든 정보에 대해 즉각적으로
          도움을 드립니다.
        </p>
      </section>
  
      <!-- 주요 기능 -->
      <section class="features">
        <h2>주요 기능</h2>
        <div class="feature-item">
          <h3>1. 실시간 질문 응답</h3>
          <p>AI가 실시간으로 여러분의 질문에 답변을 제공합니다.</p>
        </div>
        <div class="feature-item">
          <h3>2. 맞춤형 추천</h3>
          <p>사용자의 요구와 환경에 맞는 맞춤형 상담을 제공합니다.</p>
        </div>
        <div class="feature-item">
          <h3>3. 다양한 분야 지원</h3>
          <p>여러 분야의 질문에 대응하는 폭넓은 답변을 제공합니다.</p>
        </div>
      </section>
  
      <!-- 사용자 피드백 -->
      <section class="feedback">
        <h2>사용자 피드백</h2>
        <p>우리는 항상 개선을 위해 노력하고 있습니다. 아래에서 피드백을 남겨주세요!</p>
        <form @submit.prevent="submitFeedback">
          <textarea v-model="feedback" placeholder="피드백을 입력하세요..." required></textarea>
          <button type="submit">제출</button>
        </form>
      </section>
  
      <!-- 푸터 -->
      <footer class="home-footer">
        <p>&copy; 2025 AI 상담 서비스 | 모든 권리 보유</p>
      </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: "HomeView",
    data() {
      return {
        feedback: "",
      };
    },
    methods: {
      submitFeedback() {
        if (this.feedback.trim()) {
          alert("피드백이 제출되었습니다. 감사합니다!");
          this.feedback = ""; // 피드백 제출 후 필드 초기화
        }
      },
    },
  };
  </script>
  
  <style scoped>
  #home {
    font-family: 'Noto Sans KR', sans-serif;
    text-align: center;
    padding: 20px;
  }
  
  .home-header {
    background-color: #4caf50;
    color: white;
    padding: 40px;
    border-radius: 8px;
  }
  
  .home-header h1 {
    font-size: 2.5em;
  }
  
  .intro,
  .features,
  .feedback {
    margin: 20px 0;
  }
  
  .features .feature-item {
    background-color: #f9f9f9;
    padding: 15px;
    margin-bottom: 15px;
    border-radius: 8px;
  }
  
  .feedback textarea {
    width: 80%;
    height: 100px;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  .feedback button {
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .feedback button:hover {
    background-color: #45a049;
  }
  
  .home-footer {
    margin-top: 40px;
    background-color: #333;
    color: white;
    padding: 10px;
    font-size: 0.9em;
  }
  </style>
  
<template>
    <div id="home">
        <div class="container">
            <!-- 헤더 -->
            <header class="home-header">
                <h1>국민은행 AI 상담</h1>
                <p>금융 상품을 간편하게 요약하고 빠르게 안내해 드립니다</p>
            </header>
        
            <!-- 서비스 소개 -->
            <section class="intro">
                <h2>서비스 소개</h2>
                <p>
                국민은행의 대출 상품 정보를 빠르고 정확하게 요약해주는 AI 챗봇 서비스를 제공합니다. 대출 약관이나 조건이 복잡하다고 느껴질 때,
                챗봇을 통해 간편하게 요약된 정보를 얻을 수 있습니다. 언제 어디서나 손쉽게 대출 정보를 확인하세요.
                </p>
            </section>
        
            <!-- 주요 기능 -->
            <h2>주요 기능</h2>
            <section class="features">
                <div class="feature-item">
                <h3>1. 대출 약관 요약</h3>
                <p>복잡한 대출 약관을 간단하게 요약하여 빠르게 확인할 수 있습니다.</p>
                </div>
                <div class="feature-item">
                <h3>2. 실시간 상담</h3>
                <p>실시간으로 AI 챗봇이 대출 상품에 대해 친절하게 설명해 드립니다.</p>
                </div>
                <div class="feature-item">
                <h3>3. 맞춤형 정보 제공</h3>
                <p>사용자의 상황에 맞춰 대출 상품을 추천하고, 조건을 안내합니다.</p>
                </div>
            </section>
        
            <!-- 사용자 피드백 -->
            <section class="feedback">
                <h2>사용자 피드백</h2>
                <p>서비스를 사용해보시고 의견을 남겨주세요. 개선을 위해 노력하겠습니다!</p>
                <form @submit.prevent="submitFeedback">
                <textarea v-model="feedback" placeholder="피드백을 입력하세요..." required></textarea>
                <div>
                    <button type="submit">제출</button>
                </div>
                </form>
            </section>
        </div>
  
      <!-- 푸터 -->
      <footer class="home-footer">
        <p>&copy; 2025 국민은행 AI 대출 상담 서비스 | 모든 권리 보유</p>
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
    background-color: white; /* 밝은 배경색 */
  }
  
  .home-header {
    background-color: #F5D300; /* 국민은행 노란색 */
    color: #1d3c6a; /* 국민은행 파란색 */
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .home-header h1 {
    font-size: 2.8em;
    margin-bottom: 10px;
  }
  
  .home-header p {
    font-size: 1.2em;
    font-weight: 500;
  }
  
  .intro,
  .features,
  .feedback {
    margin: 40px 0;
  }
  
  .intro p {
    font-size: 1.1em;
    line-height: 1.6;
    color: #333;
  }
  
  .features {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }
  
  .feature-item {
    background-color: #ffffff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out;
  }
  
  .feature-item:hover {
    transform: translateY(-5px);
  }
  
  .feature-item h3 {
    font-size: 1.5em;
    color: #1d3c6a;
  }
  
  .feedback textarea {
    width: 80%;
    height: 120px;
    padding: 10px;
    margin-bottom: 15px;
    border-radius: 5px;
    border: 1px solid #ccc;
    font-size: 1.1em;
  }
  
  .feedback button {
    padding: 12px 25px;
    background-color: #1d3c6a; /* 파란색 */
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1.1em;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .feedback button:hover {
    background-color: #4caf50; /* 버튼 색상 변경 */
  }
  
  .home-footer {
    margin-top: 50px;
    background-color: #333;
    color: white;
    padding: 15px;
    font-size: 0.9em;
  }
  </style>
  
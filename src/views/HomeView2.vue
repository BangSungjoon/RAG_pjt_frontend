<template>
    <div class="home-container">
      <HomeBanner />
      <HomeFeatures />
      <Footer />
    </div>
</template>
  
<script>
import HomeBanner from '@/components/home/HomeBanner.vue';
import HomeFeatures from '@/components/home/HomeFeatures.vue';
import Footer from '@/components/home/footer.vue';
export default {
components: {
    HomeBanner,
    HomeFeatures,
    Footer,
},
};
</script>
  
<style scoped>
/* 홈 페이지 전용 스타일 */
.home-container {
font-family: 'Noto Sans KR', sans-serif;
}
</style>
<template>
  <div class="design">
    <p class="main-name">PROJECT</p>
    <button class="left" @click="prevSlide"><i class="fa-solid fa-circle-arrow-left"></i></button>
    
    <div class="content-wrap">
      <!-- 움직이는 슬라이드 컨테이너 -->
      <div class="content-container" :style="{ transform: `translateX(${-currentIndex * 380}px)` }">
        <div class="content" v-for="(item, index) in images" :key="index">
          <img :src="item.src" alt="카드뉴스"/>
          <p v-html="item.text"></p>
        </div>
      </div>
    </div>

    <button class="right" @click="nextSlide"><i class="fa-solid fa-circle-arrow-right"></i></button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// 이미지 데이터
const images = ref([
  { src: './images/design/d-1.jpg', text: '카드뉴스' },
  { src: './images/design/d-2.jpg', text: '카드뉴스' },
  { src: './images/design/d-3.jpg', text: '카드뉴스' },
  { src: './images/design/d-4.jpg', text: '카드뉴스' },
  { src: './images/design/d-5.png', text: '프로젝트 인터랙티브 <br> 웹 구현' },
  { src: './images/design/d-6.png', text: '프로그래스 바 <br> 애니메이션' },
  { src: './images/design/d-7.png', text: 'Chart' },
  { src: './images/design/d-8.png', text: '기념일 계산기' },
  { src: './images/design/d-9.png', text: '이미지 무한루프' },
  { src: './images/design/d-10.png', text: '구글 모멘텀 디자인' },
]);

const currentIndex = ref(0);
const itemsPerPage = 4; // 한 번에 보이는 개수
const totalItems = images.value.length; // 전체 아이템 개수

const nextSlide = () => {
  if (currentIndex.value < totalItems - itemsPerPage) {
    currentIndex.value++;
  }
};

const prevSlide = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--;
  }
};
</script>

<style lang="scss" scoped>
.design {
  width: 100%;
  height: 100vh;
  position: relative;
}

.main-name {
  font-family: 'Gyeonggi_Title_Bold';
  text-align: center;
  font-size: 60px;
  color: #222;
  padding: 60px 0; 
}

/* 감싸는 박스 (고정 크기) */
.content-wrap {
  padding: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 80%;
  height: 500px;
  overflow: hidden; /* 넘치는 요소 숨김 */
  background-color: #c3e5fa;
  border-radius: 5px;
  box-shadow: 5px 5px 3px #999;
}

/* 내부 컨테이너 (움직이는 요소) */
.content-container {
  height: 100%;
  display: flex;
  gap: 80px;
  transition: transform 0.5s ease-in-out;
  align-items: center;
}

/* 개별 카드 */
.content {
  width: 300px;
  height: 400px;
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 30px;
}

.content > img {
  width: 300px;
  height: 300px;
  border-radius: 20px;
}

.content > p {
  font-family: 'Gyeonggi_Title_Medium';
  text-align: center;
  font-size: 30px;
  padding-top: 5px;
}

button {
  border: none;
  font-size: 50px;
  background-color: transparent;
  cursor: pointer;
}

.left {
  position: absolute;
  left: 80px;
  top: 50%;
  transform: translateY(-50%);
}

.right {
  position: absolute;
  right: 40px;
  top: 50%;
  transform: translateY(-50%);
}
</style>

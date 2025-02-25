<template>
  <div class="design">
    <p class="main-name">PROJECT</p>

    <button class="left" @click="prevSlide">
      <i class="fa-solid fa-circle-arrow-left"></i>
    </button>

    <div class="content-wrap">
      <div class="content-container" 
        :style="{
           transform: `translateX(${-currentIndex * 390}px)`,
          transition: isAnimating ? 'transform 0.5s ease-in-out' : 'none'
          }">
        <div class="content" v-for="(item, index) in clonedImages" :key="index">
          <img :src="item.src" alt="카드뉴스"/>
          <p v-html="item.text"></p>
        </div>
      </div>
    </div>

    <button class="right" @click="nextSlide">
    <i class="fa-solid fa-circle-arrow-right"></i>
    </button>
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from 'vue';

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
  { src: './images/design/d-10.png', text: '구글 모멘텀 디자인' }
]);

//앞 뒤로 4개씩 이미지 추가
const clonedImages = computed(()=>{
  return [
    ...images.value.slice(-4),
    ...images.value,
    ...images.value.slice(0, 4)
  ];
});

const isAnimating = ref(true);
const currentIndex = ref(4);  //첫번째서 시작

onMounted(()=>{
  currentIndex.value = 4;
});

// 이전버튼 눌렀을 때
const prevSlide = () => {
  if(!isAnimating.value) return; //애니메이션 중 클릭 방지

  isAnimating.value =true;  
  currentIndex.value--;

  //첫번재 이미지에서 마지막으로 이동
  setTimeout(() => {
    if (currentIndex.value === 0) {
      isAnimating.value = false;
      currentIndex.value = images.value.length; // 마지막 아이템으로 이동
      setTimeout(()=>{ isAnimating.value = true}, 50);
    }
  }, 500);
};

//다음버튼 눌렀을 때
const nextSlide = () => {
  if (!isAnimating.value) return; // 애니메이션 중 클릭 방지

  isAnimating.value = true; 
  currentIndex.value++;

  setTimeout(() => {
    if (currentIndex.value === images.value.length + 4) {
      isAnimating.value = false;
      currentIndex.value = 4;
      setTimeout(() => (isAnimating.value = true), 50);
    }
  }, 500);
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

.content-wrap {
  padding: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 1500px;
  height: 500px;
  overflow: hidden; 
  background-color: #c3e5fa;
  border-radius: 5px;
  box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
}

.content-container {
  height: 100%;
  display: flex;
  gap: 90px;
  align-items: center;
}
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
  font-size: 60px;
  background-color: transparent;
  cursor: pointer;
}

.left {
  position: absolute;
  left: 90px;
  top: 50%;
  transform: translateY(-50%);
  z-index: 5;
}

.right {
  position: absolute;
  right: 90px;
  top: 50%;
  transform: translateY(-50%);
  z-index: 5;
}

//반응형

//스마트폰
@media (max-width: 600px) {
  .design {
  width: 100%;
  height: 85vh;
  position: relative;
}
  .main-name {
  font-family: 'Gyeonggi_Title_Bold';
  text-align: center;
  font-size: 50px;
  color: #222;
  padding: 50px 0; 
}

.content-wrap {
  padding: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 310px;
  height: 400px;
}
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

button {
  border: none;
  font-size: 40px;
  background-color: transparent;
  cursor: pointer;
}

.left {
  left: 20px;
}

.right {
  right: 15px;
}
}


</style>

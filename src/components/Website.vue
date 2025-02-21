<template>
  <div class="website">
    <button id="left" @click="prevSlide" :disabled="currentIdx === 0"><i class="fa-solid fa-left-long"></i></button>
    <p>WEB PURBLISING</p>
    <div class="content-wrap">
      <div class="content-slider" :style="{transform: `translateX(${-currentIdx * 100}%)`}">
        <div class="content-container" v-for="(project, idx) in projects" :key="idx">
          <div class="content">
            <video v-if="project.video" :src="project.video" controls autoplay loop muted></video>
          </div>
          <div class="p-txt">
            <p><img src="../../public/images/bubble.png" alt="말풍선이미지">프로젝트 설명</p>
            <hr>
            <p id="main">〈{{ project.title }}〉</p>
            <p class="p-word">{{ project.description }}</p>
            <hr>
            <p><img src="../../public/images/bubble.png" alt="말풍선이미지">Tech stack</p>
            <hr>
            <p id="stack" v-html="project.stack"></p>
            <hr>
            <p><img src="../../public/images/bubble.png" alt="말풍선이미지">깃허브 링크</p>
            <hr>
            <p id="link"><a :href="project.link" target="_blank">{{ project.link }}</a></p>
          </div>
        </div>
      </div>
    </div>

    <div class="dots">
      <div 
        v-for="(idx) in projects.length " 
        :key="idx" 
        class="dot" 
        :class ="{active: (currentIdx+1) === idx }" 
        @click="currentIdx = idx-1">
      </div>
    </div>

    <button id="right" @click="nextSlide" :disabled="currentIdx === projects.length -1"><i class="fa-solid fa-right-long"></i></button>
  </div>
</template>

<script setup>
import { ref } from 'vue';


const projects = ref([
  {
    title: "Tesla Clone_ HTML5 & CSS3 웹 표준 기반 구현",
    description: "실제 테슬라 웹사이트의 레이아웃과 애니메이션을 반영하여 반응형 디자인, 웹 표준 및 접근성 준수를 중심으로 개발하였습니다.",
    stack: `- UI 디자인 방식 : Figma를 이용한 디자인 구축 후 코드 구현 <br>
            - 제작에 사용된 스킬 : HTML5, CSS3 <br>
            - 레이아웃 제작 방식 : Flexbox를 활용한 구성 <br>
            - 플러그인 : FontAwesome, Google Font <br>
            - 제작기간 : 2일 <br>
            - 제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행`,
    link: "https://kwonjung9.github.io/TESLA/index.html",
    video: "../.././public/images/video/v-2.mp4"
  },
  {
    title: "Airbnb Clone_반응형 숙박 예약 웹사이트",
    description: "반응형 웹 디자인, 웹 표준 및 접근성 준수를 중심으로 개발하여 다양한 디바이스에서 최적화 된 사용자 경험을 제공하도록 개발하였습니다",
    stack: `-UI 디자인 방식 : Figma를 활용해 화면 분석 후 코딩 진행 <br>
            -제작에 사용된 스킬 : HTML5, CSS3 <br>
            -레이아웃 제작 방식 : Flexbox를 활용한 구성 <br>
            -플러그인 : Axios, react-slick, scss <br>
            -제작기간 : 2일 <br>
            -제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행
            `,
    link: "https://kwonjung9.github.io/airbnb/airbnb.html",
    video: "/videos/tesla.mp4"
  },
  {
    title: "Netflix Clone_React기반의 웹 구현",
    description: "Netflix의 주요 기능을 모방하여 React를 활용한 웹 애플리케이션을 개발하였습니다. UI/UX 구현 능력, 비동기 데이터 처리를 강조하였습니다.",
    stack: `-UI 디자인 방식 : Figma를 활용해 화면 분석 후 코딩 진행 <br>
            -제작에 사용된 스킬 : HTML5, CSS3 <br>
            -레이아웃 제작 방식 : Flexbox를 활용한 구성 <br>
            -플러그인 : Axios, react-slick, scss <br>
            -제작기간 : 2일 <br>
            -제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행
            `,
    link: "https://kwonjung9.github.io/neflix_clone/",
    video: "/videos/tesla.mp4"
  },
  {
    title: "모바일 금융 퀴즈 _React 기반의 학습 플랫폼",
    description: "이곳에 세 번째 프로젝트 설명을 추가하세요.",
    stack: `-UI 디자인 방식 : Figma를 활용하여 모바일 중심의 UX 디자인 <br>
            -제작에 사용된 스킬 : React(Hooks, useState 활용) <br>
            -레이아웃 제작 방식 : Flex box 기반의 레이아웃 <br>
            -제작기간 : 1일 <br>
            -제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행
            `,
    link: "https://kwonjung9.github.io/quizcard/",
    video: "/videos/tesla.mp4"
  },
  {
    title: "eCommerce 웹사이트 구축_Vue3 쇼핑몰",
    description: "Vue3를 이용하여 상품 정보를 보이고, 장바구니에 담고, 결제 페이지까지 이동하는 쇼핑몰 웹사이트를 개발하였습니다.",
    stack: `-제작에 사용된 스킬 : Vue3, Vue Router - 컴포넌트 기반 <br>
            -레이아웃 제작 방식 : Flex box 기반의 레이아웃 <br>
            -제작기간 : 1일 <br>
            -제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행
            `,
    link: "https://kwonjung9.github.io/products/#/",
    video: "/videos/tesla.mp4"
  },
  {
    title: "블로그형 홈페이지",
    description: "디자인을 직접 기획하고, HTML+CSS를 활용하여 반응형 및 사용자 경험을 고려한 사이트를 개발하였습니다. ",
    stack:  `-UI 디자인 방식 : photoshop을 이용한 디자인 기획 디자인 <br>
            -제작에 사용된 스킬 :  HTML5, CSS3 <br>
            -레이아웃 제작 방식 : Flex box 기반의 레이아웃 <br>
            -제작기간 : 1일 <br>
            -제작 참여율 : 100%(개인프로젝트) <br>
            기획, UI디자인, 개발, 배포까지 전 과정 직접 수행
            `,
    link: "https://kwonjung9.github.io/blog/blog.html",
    video: "/videos/tesla.mp4"
  },
]);

const currentIdx = ref(0);

const prevSlide = () => {
  console.log("이전버튼");
  if (currentIdx.value > 0) {
    currentIdx.value--;
  }
};

const nextSlide =()=>{
  if (currentIdx.value < projects.value.length -1){
    currentIdx.value++;
  }
}

</script>

<style lang="scss" scoped>
.website {
  width: 100%;
  height: 100vh;
  background-color: #BDE6FF;
  position: relative;
}

.website > p {
  font-family: 'Gyeonggi_Title_Bold';
  text-align: center;
  font-size: 60px;
  color: #222;
  padding: 60px 0;
}

.content-wrap {
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-slider {
  display: flex;
  width: 100%;
  transition: transform 0.5s ease-in-out;
}

.content-container {
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 100px;
  align-items: center;
  flex-shrink: 0;
}

.content {
  width: 800px;
  height: 650px;
  background-color: #ffffff;
  border-radius: 20px;
}

.content video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 20px;
}

.p-word{
  word-break: keep-all;
}

.p-txt {
  font-family: 'Gyeonggi_Title_Light';
  background-color: #dddddd;
  border: 1px solid silver;
  border-radius: 20px;
  width: 500px;
  height: 610px;
  padding: 20px;
}

.p-txt > p {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 20px;
  line-height: 40px;
}

.p-txt > p img {
  width: 20px;
  height: 20px;
}

.p-txt > hr{
  width: 100%;
}

#main {
  font-family: 'Gyeonggi_Title_Medium';
}

#stack {
  font-size: 19px;
  line-height: 40px;
}

#link {
  font-size: 18px;
}



.dots {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 10px;
}

.dot {
  width: 20px;
  height: 20px;
  background-color: #ffffff;
  border-radius: 50%;
  cursor: pointer;
}

.dot.active {
  background-color: #eeeeee;
  border: 1px solid #777777;
}

#left, #right {
  background-color: transparent;
  border: none;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 50px;
  cursor: pointer;
}

#left {
  left: 40px;
  z-index: 5;
}

#right {
  right: 40px;
}
</style>

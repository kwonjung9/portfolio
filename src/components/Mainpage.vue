<template>

  <div class="container">
    <div class="line">
      <div class="bar" :style="{width:`${percent}%`}"></div>
    </div>
    <ul>
      <li @click="scrollTo('about')">ABOUTME</li>
      <li @click="scrollTo('website')">WEB PURBLISING</li>
      <li @click="scrollTo('design')">PROJECT</li>
      <li @click="scrollTo('contact')">CONTACT</li>
      <li v-if="menubar" class="menubar" @click="menu"><img src="../../public/images/menubar.png" alt=""></li>
    </ul>
  <div class="introduce-wrap">
    <div class="introduce-img"></div>
    <div class="introduce-txt">
      <p>JungEun Kwon's <br>PORTFOLIO :）</p>
      <p>안녕하세요! <br>프론트앤드 개발자<br> 권정은 입니다 .</p>
    </div>
    <button v-if="showBtn" class="top" @click="handletop">TOP</button>
  </div>
  </div>
</template>

<script setup>

import { onMounted, onUnmounted, ref } from 'vue';

const emit = defineEmits(['scroll-to-section']);

const percent = ref(0);
const showBtn = ref(false);
const menubar = ref(false);


const scrollTo = (section) => {
  emit('scroll-to-section', section);
};

const handleScroll =()=>{
  const {scrollTop, clientHeight, scrollHeight} = document.documentElement;
  percent.value = (scrollTop/(scrollHeight-clientHeight))*100;
  showBtn.value = scrollTop > 50;
}

const handletop =()=>{
    window.scrollTo({ top:0, behavior:"smooth" });
  }

onMounted(()=>{
    window.addEventListener("scroll", handleScroll);
  });
  onUnmounted(()=>{
    window.removeEventListener("scroll",handleScroll);
  });
</script>

<style lang="scss" scoped>
.app{
    width: 100vw;
    height: 100vh;
  }
  .line{
    width: 95%;
    border: none;
    box-sizing: border-box;
    position: fixed;
    top: 10px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 30;

  }
  .bar{
    border-radius: 50px;
    height: 10px;
    background-color: rgba($color: #ddd, $alpha: 0.3);
  }
  ul{
    font-family: 'Gyeonggi_Title_Medium';
    margin: 30px 0;
    background-color: #EAEAEA;
    width: 100%;
    height: 100px;
    display: flex;
    gap: 20px;
    justify-content: end;
    align-items: center;
  }
  ul > li{
    padding-right: 40px;
    font-weight:lighter;
    font-size: 1.3rem;
  }
  ul > li:hover{
    color: #666;
    cursor: pointer;
  }
  .introduce-wrap{
    background-color: #BDE6FF;
    height: 650px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 300px;
    margin-top: 40px;
    padding: 15px 0;
    position: relative;
  }
  .introduce-img{
    background-color: blueviolet;
    width: 450px;
    height: 450px;
    border-radius: 50%;
  }
  .introduce-txt > p:nth-of-type(1){
    font-family: 'Ownglyph_ParkDaHyun';
    font-weight: 700;
    font-size: 60px;
    text-shadow: 5px 5px 5px rgba(255, 255, 255, 0.8);
    margin-bottom: 30px;
    line-height: 90px;
    letter-spacing:15px;
  }
  .introduce-txt > p:nth-of-type(2){
    font-size: 35px;
    text-align: left;
    line-height: 70px;
    font-family: 'Gyeonggi_Title_Bold';
  }
  .top{
  font-family: 'Ownglyph_ParkDaHyun';
  font-size: 25px;
  position: fixed;
  bottom: 10%;
  right: 25px;
  width: 60px;
  height: 60px;
  border: 1px solid #888;
  outline: none;
  background-color: #b1d9f0;
  padding: 5px;
  border-radius: 50px;
  cursor: pointer;
  z-index: 10;
  box-shadow: inset 0 0 5px #999999;
}
//반응형

// 스마트폰

@media (max-width: 480px) {
  .top{
  font-size: 18px;
  bottom: 10%;
  right: 5%;
  width: 50px;
  height: 50px;
}
  .line{
    visibility: hidden;
  }
  ul{
    margin: 5px 0;
    justify-content: center;
  }
  ul > li{
    font-weight:lighter;
    font-size: 14px;
    padding-right: 1px;
  }
  .introduce-wrap{
    width: 100%;
    height: 550px;
    gap: 20px;
    display: flex;
    flex-direction: column;
  }

  .introduce-img{
    background-color: blueviolet;
    width: 200px;
    height: 200px;
    border-radius: 50%;
  }
  .introduce-txt > p:nth-of-type(1){
    font-family: 'Ownglyph_ParkDaHyun';
    font-size: 40px;
    text-shadow: 5px 5px 5px rgba(255, 255, 255, 0.8);
    margin-bottom: 20px;
    line-height: 50px;
    letter-spacing:10px;
    text-align: center;
  }
  .introduce-txt > p:nth-of-type(2){
    text-align: center;
    font-size: 20px;
    line-height: 30px;
    letter-spacing:5px;
  }
}

//태블릿

@media (min-width: 480px) and (max-width: 1440px) {
  .top{
  font-size: 20px;
  bottom: 5%;
  right: 5%;
  width: 55px;
  height: 55px;
  }
  .line{
    visibility: hidden;
  }
  .container{
    width: 100vw;
  }
  ul{
    margin: 5px 0;
    width: 100%;
    justify-content: center;
  }
  ul > li{
    font-weight:lighter;
    font-size: 18px;
    padding-right: 3px;
  }
  .introduce-wrap{
    width: 100%;
    height: 600px;
    gap: 20px;
    display: flex;
    flex-direction: column;
  }

  .introduce-img{
    background-color: blueviolet;
    width: 250px;
    height: 250px;
    border-radius: 50%;
  }
  .introduce-txt > p:nth-of-type(1){
    font-family: 'Ownglyph_ParkDaHyun';
    font-size: 45px;
    text-shadow: 5px 5px 5px rgba(255, 255, 255, 0.8);
    margin-bottom: 20px;
    line-height: 50px;
    letter-spacing:10px;
    text-align: center;
  }
  .introduce-txt > p:nth-of-type(2){
    text-align: center;
    font-size: 30px;
    line-height: 40px;
    letter-spacing:5px;
  }
}


</style>
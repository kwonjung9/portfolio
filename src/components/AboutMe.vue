<template>
  <div class="about">
    <div class="About-Me">
      <div class="main-txt">
        <img src="../../public/images/smile.png" alt="스마일1">
        <span>About Me</span>
        <img src="../../public/images/smile.png" alt="스마일2">
      </div>
      <div class="content-txt">
        <p>긍정적인 사고방식을 바탕으로 어떤 도전이든<br/> 성공적인 결과로 이끌기 위해 최선을 다하고 있습니다.</p> 
        <p>사용자에게 더 나은 경험을 제공하기 위해<br/> 팀원들과 원활한 소통을 하는 것을 좋아합니다.</p>
      </div>
    </div>
    <div class="sklls">
      <p>sklls</p>
      <div class="img-wrap">
        <div class="img">
        <img src="../../public/images/html.png" alt="html">
        <span>HTML</span>
        </div>
        <div class="img">
        <img src="../../public/images/css.png" alt="css">
        <span>CSS3</span>
        </div>
        <div class="img">
        <img src="../../public/images/javascript.png" alt="javascript">
        <span>javascript</span>
        </div>
        <div class="img">
        <img src="../../public/images/react.png" alt="react">
        <span>React</span>
        </div>
        <div class="img">
        <img src="../../public/images/vue.png" alt="vue">
        <span>Vue</span>
        </div>
        <div class="img">
        <img src="../../public/images/Photoshop .png" alt="photoshop">
        <span>photoshop</span>
        </div>
        <div class="img">
        <img src="../../public/images/Illustrator .png" alt="Illustrator">
        <span>Illustrator</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.about{
  font-family: 'Gyeonggi_Title_Bold';
  width: 100%;
  height: 100vh;
  text-align: center;
}
.about  p{
  font-size: 30px;
  line-height: 60px;
}
.main-txt{
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 50px;
  font-size: 60px;
  padding: 60px 0;

}
.main-txt > img{
  width: 60px;
  height: 60px;
}
.sklls{
  padding: 50px 0;
}
.sklls > p{
  padding: 20px 0;
  font-size: 40px;
  font-family: 'Gyeonggi_Title_Medium';
}
.sklls  img{
  width: 130px;
  height: 130px;
}
.img-wrap{
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 60px;
  padding: 30px 0;
}
.img{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  font-size: 20px;
}
span{
  font-family: 'Gyeonggi_Title_Medium';
}

//반응형

// 스마트폰

@media (max-width: 480px) {
  .about{
  font-family: 'Gyeonggi_Title_Bold';
  width: 100%;
  height: 100vh;
  text-align: center;
  }
  .main-txt{
  gap: 20px;
  font-size: 50px;
  padding: 50px 0;
  font-family: 'Gyeonggi_Title_Bold';
}
.main-txt > img{
  width: 50px;
  height: 50px;
}
.about  p{
  font-size: 20px;
  line-height: 50px;
}
.sklls{
  padding: 35px 0;
}
.sklls > p{
  padding: 20px 0;
  font-size: 40px;
  font-family: 'Gyeonggi_Title_Medium';
}
.sklls  img{
  width: 70px;
  height: 70px;
}
.img-wrap{
  flex-wrap: wrap;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  padding: 30px 0;
  line-height: 30px;
}
.img{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 15px;
  font-size: 20px;
}
}

//태블릿

@media (min-width: 480px) and (max-width: 1440px) {
  .about{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  font-family: 'Gyeonggi_Title_Bold';
  width: 100%;
  height: 90%;
  text-align: center;
  }
  .main-txt{
  gap: 35px;
  font-size: 55px;
  padding: 50px 0;
  font-family: 'Gyeonggi_Title_Bold';
}
.main-txt > img{
  width: 55px;
  height: 55px;
}
.about  p{
  font-size: 25px;
  line-height: 55px;
}
.sklls{
  padding: 40px 0;
}
.sklls > p{
  padding: 15px 0;
  font-size: 40px;
  font-family: 'Gyeonggi_Title_Medium';
}
.sklls  img{
  width: 70px;
  height: 70px;
}
.img-wrap{
  flex-wrap: wrap;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  padding: 30px 0;
  line-height: 30px;
}
.img{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  font-size: 22px;
}
}
</style>
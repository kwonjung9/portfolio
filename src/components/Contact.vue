<template>
  <div class="contact">
    <p class="main-txt">Contact</p>
    <div class="images">
      <a href="https://github.com/kwonjung9"><img src="../../public/images/girhub.png" alt="깃허브"></a>
      <a href="tel:01032069706"><img src="../../public/images/call.png" alt="전화"></a>
      <a href="mailto:wjd994899@naver.com"><img src="../../public/images/email.png" alt="이메일"></a>
    </div>
    <p class="reserved">© 2025. Jungeun Kwon . All rights reserved.</p>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
  .contact{
    width: 100%;
    height: 300px;
    background-color: #EAEAEA;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 30px;
    font-family: 'Gyeonggi_Title_Light';
  }
  .contact > .main-txt{
    font-family: 'Gyeonggi_Title_Medium';
    font-size: 30px;
  }
  .contact a img {
    width: 40px;
    height: 40px;
  }
  .images{
    display: flex;
    gap: 40px;
  }

  // 반응형

  // 스마트폰
  @media (max-width: 600px) {
    .contact{
      height: 15vh;
      gap: 15px;
  }
  .contact > .main-txt{
    font-size: 20px;
  }
  .contact a img{
    width: 30px;
    height: 30px;
  }
  .images{
    gap: 30px;
  }
  .reserved{
    font-size: 10px;
    color: #444;
  }
}  

</style>
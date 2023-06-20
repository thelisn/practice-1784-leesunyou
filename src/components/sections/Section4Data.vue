<template>
  <section class="section4">
    <div class="section4_bg">
      <div class="roll">
        <div v-for="item in item" class="textbox">
          <p class="text">{{ text }}</p>
          <p class="arrow">{{ arrow }}</p>
        </div>
      </div>
      <h2 class="main_title">TECH</h2>

      <div class="tech_cont">
        <p class="sub_title">로봇과 함께하는 일상</p>
        <p class="desc_1">
          로봇이 우리 삶에 자연스럽게 녹아드는 세상을 준비합니다.
          <br>
          이를 앞당길 거대한 실험이 1784에서 시작되었습니다.
          <br>
          네이버의 로보틱스, 자율주행, AI, 5G, 클라우드 기술과
          <br>
          혁신적 인프라들이 하나로 융합됩니다.
        </p>
        <p class="desc_2">
          세계 최초 로봇 친화형 건물 - 스마트도시협회 인증 2022
        </p>
        <div class="tech_main_img">
          <img src="@/assets/images/section4/tech.jpg" alt="naver1784">
        </div>

        <div class="tech_box">
          <img src="" alt="">
          <p class="box_name"></p>
          <p class="box_desc"></p>
        </div>
      </div>

    </div>
  </section>
</template>

<script>

</script>

<style scoped lang="scss">
.section4 {
  position: relative;
  top: 3000px;
  width: 100%;
  height: 500vh;
  background: pink;

  


}
</style>
<template>
  <section class="section3">
    <p class="title">
      건물이 기술 그 자체
    </p>
    <div class="desc">
      <p class="desc1">기술은 혼자 존재할 때 보다 서로 연결되고 합쳐질 때</p>
      <p class="desc1">더 큰 의미를 갖습니다.</p>

      <p class="desc2">공간-기술-사람-로봇이 촘촘히 연결되고 융합되는</p>
      <p class="desc2">도전 속에 일상을 변화시킬 새로움을 만드는 것,</p>
      <p class="desc2">이것이 우리가 테크 컨버전스에 집중하는 이유입니다.</p>
    </div>
    <div class="video_wrap">
      <div class="video">
        <!-- img :src에 require 넣지 않으면 이미지가 나타나지 않음 -->
        <img
          v-for="(item, itemIndex) in 500"
          :key="`item-${itemIndex}`"
          :class="[`img_${item}`, { active: item === imgFrame }]"
          :src="require(`@/assets/images/section3/0${item.toString().padStart(3, '0')}.jpg`)"
        >
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Section3',
  computed: {

    bgOpacity() {
      return Math.min(60, this.scrollTop - 450) * 0.02
    },

    titleTransform() {
      return `translate(-50%, -${this.scrollTop - 500}%)`
    },

    titleOpacity() {
      if (this.scrollTop < 550)
        return Math.min(60, this.scrollTop - 500) * 0.05
      return 1 - Math.min(60, this.scrollTop - 580) * 0.05
    },

    descDisplay() {
      if (this.scrollTop < 100)
      return `none`
    },
    
    descTransform() {
      return `translate(-50%, -${this.scrollTop - 600}%)`
    },
    
    descOpacity() {
      return Math.min(30, this.scrollTop - 620) * 0.03
    },

    imgTransform() {
      return `translate(-50%, calc(-50% + ${(25 - Math.min(25, Math.max(0, (this.scrollTop - 350)))) * 0.5}%))`
    },

    imgWidth() {
      return `${Math.min(100, Math.max(80, (this.scrollTop - 710)) * .5)}%`
    },

    imgHeight() {
      return `${Math.min(100, Math.max(0, (this.scrollTop - 710)) * .5)}%`
    },

    imgFrame() {
      return Math.ceil(Math.min(500, Math.max(1, (this.scrollTop - 930))))
    },

    imgDisplay() {
      if (this.scrollTop > 2000)
        return `none`
    }
  },

  props: ['scrollTop']
}
</script>

<style scoped lang="scss">
.section3 {
  position: relative;
  width: 100vw;
  height: 880vh;
  margin-top: -200vh;
  background: #000;
  opacity: v-bind('bgOpacity');

  .title {
    display: v-bind('descDisplay');
    position: fixed;
    top: 50%;
    left: 50%;
    color: #fff;
    font-size: 9em;
    text-align: center;
    font-family: 'NanumSquareNeoExtraBold';
    transform: v-bind('titleTransform');
    opacity: v-bind('titleOpacity');
    white-space: nowrap;
  }

  .desc {
    display: v-bind('descDisplay');
    position: fixed;
    top: 50%;
    left: 50%;
    color: #fff;
    font-size: 2.6em;
    text-align: center;
    line-height: 40px;
    transform: v-bind('descTransform');
    opacity: v-bind('descOpacity');

    .desc1:nth-child(2) {
      margin-bottom: 30px;
    }
  }

  .video_wrap {
    position: fixed;
    top: 50%;
    left: 50%;
    width: v-bind('imgWidth');
    height: v-bind('imgHeight');
    transform: v-bind('imgTransform');

    .video {
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;

      img {
        display: v-bind('imgDisplay');
        position: absolute;
        top: 50%;
        left: 50%;
        width: 100%;
        height: 100%;
        transform: translate(-50%, -50%);
        opacity: 0;
        object-fit: cover;

        &.active {
          opacity: 1;
        }
      }
    }
  }
}
</style>
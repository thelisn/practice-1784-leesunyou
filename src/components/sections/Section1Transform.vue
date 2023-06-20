<template>
  <div class="section1">
    <div class="video">
      <video muted autoplay loop>
        <source src="@/assets/video/section1.mp4" type="video/mp4">
      </video>
    </div>
    <div class="bg_filter">
      <div class="title_wrap">
        <p class="title">1784</p>
      </div>

      <p class="the">THE</p>
      <p class="test">TEST</p>
      <p class="bed">BED</p>

      <div class="arrow">
        <p>&#8659;</p>
      </div>

      <div class="naver_img">
        <img src="@/assets/images/naver.svg" alt="NAVER">
      </div>

      <div class="desc">
        <p class="desc_1 desc1">1784는 네이버의 새로운 사옥이 가진 이름이자</p>
        <p class="desc_2 desc1">지번이며, 최초의 산업혁명이 시작된 해입니다.</p>
        <p class="desc_3 desc2">산업혁명이 인류의 삶을 바꿔 놓았던 것처럼,</p>
        <p class="desc_4 desc2">1784를 거대한 TESTBED 삼아 끊임없이</p>
        <p class="desc_5 desc2">실험하고 도전하며 새로운 내일을 만들어 갑니다.</p>

        <div class="brand_film go">
          <a href="#" onclick="return false">
            <p class="brand_title">브랜드 필름 보기</p>
            <p class="brand_arrow">&#8680;</p>
          </a>
        </div>

        <div class="story_now go">
          <a href="#" onclick="return false">
            <p class="story_title">스토리 바로 보기</p>
            <p class="story_arrow">&#8681;</p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Section1',

  data() {
    return {

    }
  },

  computed: {
    videoDisplay() {
      if (this.scrollTop > 900)
        return `none`
    },

    titleTransform() {
      return `translate3d(
      ${-50 - Math.min(32, Math.max(0, (this.scrollTop - 150) * 1.5))}%,
      ${-50 - Math.min(145, Math.max(0, (this.scrollTop - 200) * 3.64))}%,
      ${Math.max(-260, -(this.scrollTop * 2))}px)`
    },

    titleOpacity() {
      return 1 - Math.min(60, this.scrollTop - 300) * 0.06
    },

    mainOpacity() {
      if (this.scrollTop < 300)
        return Math.min(40, this.scrollTop - 200) * 0.03
      return 1 - Math.min(60, this.scrollTop - 300) * 0.06
    },

    theRight() {
      if (this.scrollTop < 250)
        return Math.min(40, (this.scrollTop - 200)) + '%'
      return 40 + (this.scrollTop - 250) * 0.5 + '%'
    },

    testRight() {
      if (this.scrollTop < 250)
        return 100 - Math.min(40, (this.scrollTop - 200)) + '%'
      return 60 - (this.scrollTop - 250) * 0.5 + '%'
    },

    bedRight() {
      if (this.scrollTop < 250)
        return Math.min(40, (this.scrollTop - 200)) + '%'
      return 40 + (this.scrollTop - 250) * 0.5 + '%'
    },

    arrowOpacity() {
      return 1 - Math.min(60, this.scrollTop - 300) * 0.06
    },

    naverOpacity() {
      if (this.scrollTop < 400)
        return Math.min(20, this.scrollTop - 380) * 0.05
      return 1 - Math.min(20, this.scrollTop - 400) * 0.05
    },

    naverTransform() {
      return 'translate(-50%,' + (200 - this.scrollTop) + 'px)'
    },

    desc1Opacity() {
      return Math.min(30, this.scrollTop - 430) * 0.03
    },

    desc2Opacity() {
      return Math.min(30, this.scrollTop - 470) * 0.03
    },

    goOpacity() {
      return Math.min(30, this.scrollTop - 510) * 0.03
    }
  },

  props: ['scrollTop'],
}

// window.addEventListener('scroll', function () {
//   console.log(window.scrollY)
// });
// 스크롤 위치 구하기
</script>

<style scoped lang="scss">
.section1 {
  overflow: hidden;
  position: relative;
  width: 100%;
  height: 750vh;
  background: #000;

  .video {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    video {
      display: v-bind('videoDisplay');
      position: relative;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .bg_filter {
    position: absolute;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);

    .title_wrap {
      position: fixed;
      perspective: 50px;
      // background: yellow;
      width: 100vw;
      height: 100vh;

      .title {
        position: fixed;
        top: 50%;
        left: 50%;
        color: #fff;
        font-size: 80em;
        font-family: 'NanumSquareNeoExtraBold';
        text-align: center;
        transform: v-bind('titleTransform');
        opacity: v-bind('titleOpacity');
        // background-color: pink;
      }
    }

    .the,
    .test,
    .bed {
      position: fixed;
      top: 50%;
      color: #fff;
      font-size: 12em;
      font-family: 'NanumSquareNeoExtrabold';
      opacity: v-bind('mainOpacity');
    }

    .the {
      right: v-bind('theRight');
      transform: translate(20%, -100%);
    }

    .test {
      right: v-bind('testRight');
      transform: translate(70%, 0%);
    }

    .bed {
      right: v-bind('bedRight');
      transform: translate(20%, 100%);
    }

    .arrow {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      opacity: v-bind('arrowOpacity');
      animation: arrow .9s ease-in-out infinite;

      @keyframes arrow {
        0% {
          bottom: 30px;
        }

        50% {
          bottom: 23px;
        }

        100% {
          bottom: 30px
        }
      }

      p {
        color: #fff;
        font-size: 4em;
      }
    }

    .naver_img {
      position: fixed;
      top: 70%;
      left: 50%;
      width: 360px;
      transform: v-bind('naverTransform');
      opacity: v-bind('naverOpacity');
    }

    .desc {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

      .desc_1,
      .desc_2,
      .desc_3,
      .desc_4,
      .desc_5 {
        color: #fff;
        font-size: 2.6em;
        text-align: center;
        line-height: 40px;
      }

      .desc_2 {
        margin-bottom: 30px;
      }

      .desc1 {
        opacity: v-bind('desc1Opacity');
      }

      .desc2 {
        opacity: v-bind('desc2Opacity');
      }

      .go {
        transition: .5s;
        opacity: v-bind('goOpacity');
      }

      .brand_film {
        width: 500px;
        height: 70px;
        margin: 0 auto;
        margin-top: 60px;
        border: 4px solid #fff;
        border-radius: 35px;

        &:hover {
          background: rgba(0, 0, 0, .6);
        }

        a {
          display: block;
          position: relative;
          width: 100%;
          height: 62px;
          border-radius: 30px;

          p {
            display: inline-block;
            color: #fff;
            font-size: 2.2em;
          }

          .brand_title {
            margin-top: 20px;
            margin-left: 35px;
          }

          .brand_arrow {
            margin-left: 250px;
          }
        }
      }

      .story_now {
        width: 500px;
        height: 70px;
        margin: 0 auto;
        margin-top: 30px;
        border: 1px solid #fff;
        border-radius: 35px;
        background: #fff;

        &:hover {
          background: #000;
        }

        &:hover p {
          color: #fff;
        }

        a {
          display: block;
          position: relative;
          width: 100%;
          height: 62px;
          border-radius: 30px;

          p {
            display: inline-block;
            color: #000;
            font-size: 2.2em;
            transition: .4s;
          }

          .story_title {
            margin-top: 23px;
            margin-left: 35px;
          }

          .story_arrow {
            margin-left: 250px;
            transform: translateY(3px);
          }
        }
      }
    }
  }
}
</style>
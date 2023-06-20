<template>
  <header>
    <div class="header">
      <a href="@/App.vue">
        <h1 class="logo">
          1784<span> THE TESTBED</span>
        </h1>
      </a>

      <div class="story">
        <a href="#" onclick="return false">
          <p>스토리</p>
        </a>
      </div>

      <div class="lang">
        <button>
          <img src="@/assets/images/globe.svg" alt="언어">
          <p>KR</p>
          <span>&#9662;</span>
        </button>
      </div>
    </div>
  </header>
</template>

<script>

</script>

<style scoped lang="scss">
header {
  position: fixed;
  z-index: 9;
  width: 100%;
  height: 65px;
  background: rgba(0, 0, 0, .1);
  backdrop-filter: saturate(180%) blur(20px);

  .header {
    position: relative;
    width: 90%;
    height: 100%;
    margin: 0 auto;

    a {

      h1 {
        display: inline-block;
        position: relative;
        top: 20px;
        left: 0;
        margin: 0;
        color: #fff;
        font-size: 2.4em;
        font-family: 'NanumSquareNeoExtraBold';
      }
    }

    .story {
      display: inline-block;
      position: absolute;
      top: 12px;
      right: 90px;
      width: 80px;
      height: 40px;
      border: 1px solid #fff;
      border-radius: 25px;

      a {

        p {
          position: relative;
          top: 11px;
          color: #fff;
          font-size: 1.5em;
          text-align: center;
        }
      }
    }

    .lang {
      position: absolute;
      top: 19px;
      right: 0;
      width: 70px;

      button {
        height: 25px;

        img {
          display: inline-block;
          width: 25px;
          filter: invert(98%) sepia(8%) saturate(984%) hue-rotate(218deg) brightness(119%) contrast(100%);
        }

        p {
          display: inline-block;
          margin-left: 5px;
          color: #fff;
          font-size: 1.5em;
          font-family: 'NanumSquareNeoExtraBold';
          transform: translateY(-8px);
        }

        span {
          position: absolute;
          top: 8px;
          margin-left: 7px;
          color: #fff;
        }
      }
    }
  }
}
</style>

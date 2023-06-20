<template>
  <footer class="footer">
    <a href="@/App.vue" class="naver_logo">
      <div class="logo_wrap">
        <img src="@/assets/images/footer/logo.png" alt="naver">
      </div>
    </a>

    <p class="sub">1784</p>

    <ul class="site">
      <li><a href="#" onclick="return false">NAVER CLOUD</a></li>
      <li><a href="#" onclick="return false">WORKS MOBILE</a></li>
      <li><a href="#" onclick="return false">SNOW</a></li>
      <li><a href="#" onclick="return false">NAVER LABS</a></li>
      <li><a href="#" onclick="return false">NAVER WEBTOON</a></li>
      <li class="last_li"><a href="#" onclick="return false">NAVER FINANCIAL</a></li>
    </ul>

    <p class="copy">
      Copyright @ NAVER corp. All rights reserved.
    </p>
  </footer>
</template>

<script>

</script>

<style scoped lang="scss">
footer {
  position: relative;
  width: 100%;
  height: 180px;
  background: #000;

  .naver_logo {

    .logo_wrap {
      position: absolute;
      top: 30px;
      width: 120px;
      margin-left: 100px;

      img {
        width: 100%;
      }
    }
  }

  .sub {
    position: absolute;
    top: 30px;
    right: 100px;
    color: #fff;
    font-size: 2.5em;
  }

  .site {
    display: flex;
    position: absolute;
    top: 90px;
    left: 100px;

    li {

      &::after {
        margin-right: 15px;
        margin-left: 15px;
        color: #777;
        content: '|';
      }

      a {
        color: #fff;
        font-size: 1.4em;
        border-bottom: 1px solid transparent;
        padding-bottom: 2px;
        transition: .2s;

        &:hover {
          border-bottom: 1px solid #fff;
        }
      }
    }

    .last_li {

      &::after {
        content: none;
      }
    }
  }

  .copy {
    position: absolute;
    bottom: 30px;
    left: 100px;
    font-size: 1.4em;
    color: #aaa;
  }
}
</style>
<template>
  <div class="top-bar">
    <div class="topbar-action">
      <div class="join">
        <a class="v-btn">
          <img src="../../assets/img/icons/2.png">
          انضم الينا
        </a>
      </div>
      <div class="number">
        <a class="v-btn">
          <img src="../../assets/img/icons/3.png">
          اتصل بنا 
        </a>
        <b>908 566 95 010</b>
      </div>
    </div>
    <div class="lang">English</div>
    <div class="logo">
      <img src="../../assets/img/Logo.jpg">
    </div>
  </div>
</template>

<style lang="scss">
@import '../../assets/config';

.top-bar {
  height: 35px;
  background: $prim;
  display: flex;
  color: #FFF;
  align-items: center;
  padding: 20px;

  .topbar-action {
    display: flex;
    margin-right: 65px;

    div {
      display: flex;
      align-items: center;

      a {
        display: flex;
        align-items: center;
        color: #FFF;
        padding: 0 10px;
        line-height: 50px;

        img {
          max-width: 30px !important;
          margin-left: 10px;
          position: static !important;
        }
      }

      b {
        margin-right: 20px;
        font: 500 18px Roboto;
      }
    }
  }

  .lang {
    border-left: 1px solid #FFF;
    padding-left: 10px;
    font-size: 20px;
    font-weight: 500;
    position: absolute;
    left: calc(10% + 160px);
    display: block;
  }

  .logo {
    position: absolute;
    display: flex;
    left: 10%;
    top: 0;

    img {
      max-width: 130px !important;
      z-index: 7;
      box-shadow: 3px 3px 5px 0 #0003;
      margin-right: 25px;
      border-bottom-right-radius: 5px;
      border-bottom-left-radius: 5px;
    }
  }
}

@media screen and (max-width: 960px){

  .top-bar {
    padding-right: 0 !important;

    .lang {
      display: none !important;
    }

    .topbar-action {
      margin-right: 10px !important;

      div {
        font-size: 14px;

        img {
          width: 25px !important;
        }
      }

      b {
        font-size: 14px !important;
      }
    }
    .logo {
      display: none !important;
    }
  }

}
</style>
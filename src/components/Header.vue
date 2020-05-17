<template>
  <header class="Header">
    <div class="top-bar">
      <div class="topbar-action">
        <div class="join">
          <a class="v-btn">
            <img src="../assets/img/icons/2.png">
            انضم الينا
          </a>
        </div>
        <div class="number">
          <a class="v-btn">
            <img src="../assets/img/icons/3.png">
            اتصل بنا 
          </a>
          <b>908 566 95 010</b>
        </div>
      </div>
      <div class="lang">English</div>
      <div class="logo">
        <img src="../assets/img/Logo.jpg">
      </div>
    </div>

    <v-app-bar class="white" elevation="0" height="64px">

      <img class="logo2" src="../assets/img/Logo.jpg">

      <div class="search">
        <span>
          <v-icon>fa fa-search</v-icon>
        </span>
        <input type="text" placeholder="بحث...">
      </div>

      <v-list class="d-flex">
        <v-list-item router to='/'>الرئيسية</v-list-item>
        <v-list-item router to='/'>
          خدماتنا
          <v-icon small>fa fa-chevron-down</v-icon>
        </v-list-item>
        <v-list-item router to='/'>من نحن</v-list-item>
        <v-list-item router to='/'>اخر الأخبار</v-list-item>
      </v-list>
    </v-app-bar>

    <v-carousel class="carousel" hide-delimiter-background>
      <v-carousel-item v-for="i in carouselItems" :key="i.num">
        <img :src="getImgUrl(i.num)">
        <div class="content">
          {{i.content}}
        </div>
      </v-carousel-item>
    </v-carousel>
  </header>
</template>

<script>
export default {
  data() {
    return {
      carouselItems: [
        {num: 1, content: "نلتزم بالتميز في تقديم خدمات طبية عالية الجودة"},
        {num: 2, content: "نلتزم بالتميز في تقديم خدمات طبية عالية الجودة"},
        {num: 3, content: "نلتزم بالتميز في تقديم خدمات طبية عالية الجودة"},
        {num: 4, content: "نلتزم بالتميز في تقديم خدمات طبية عالية الجودة"}
      ]
    }
  },

  methods: {
    getImgUrl(pic) {
      let images = require.context('../assets/img/carousel', false, /\.jpg$/)
      return images('./' + pic + ".jpg")
    }
  },
}
</script>

<style lang="scss">
@import '../assets/config';

.Header {

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
          // font-size: 18px;
          padding: 0 10px;
          line-height: 50px;
          font-family: 'Cairo';

          img {
            max-width: 30px !important;
            margin-left: 10px;
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
        z-index: 5;
        box-shadow: 3px 3px 5px 0 #0003;
        margin-right: 25px;
        border-bottom-right-radius: 5px;
        border-bottom-left-radius: 5px;
      }
    }

  }

  .v-app-bar {
    padding: 0 10% !important;
    position: relative;

    .logo2 {
      display: none;
    }

    .search {
      display: flex;
      align-items: center;

      span {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 30px !important;
        background: $prim;
        width: 30px;

        i {
          color: #FFF;
          font-size: 16px;
        }
      }

      input {
        border: 1px solid #3337;
        border-right: none;
        direction: ltr;
        padding: 2px 10px;
        display: flex;
        align-items: center;
        position: relative;
        width: 200px;

        &::placeholder {
          position: absolute;
          top: 10%
        }
      }
    }

    .v-list {
      margin-right: 8%;
      height: 100%;

      .v-list-item {
        width: 100px;
        font: 600 16px 'Cairo';
        color: #444;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;

        span {
          border-radius: 5px !important;
        }

        i {
          margin-right: 5px;
          font-size: 16px;
        }

        &:hover {
          color: $prim;
        }
        
        &::before {
          background: transparent !important;
        }
      }
    }
  }

  .carousel {
    height: calc(100vh - 99px) !important;

    .v-responsive {
      height: 100% !important;
      position: relative;

      img {
        width: 100%;
      }

      &::after {
        content: '';
        position: absolute;
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
        background: rgba($color: #000000, $alpha: .5);
      }
    }

    .v-carousel__controls {
      bottom: 10px;
      padding-bottom: 20px;
      border-bottom: 5px solid #FFF;

      .v-btn {
        border: 3px solid #FFF;
        width: 20px;
        height: 20px;

        &.v-item--active {
          background: #FFF
        }
      }

      .mdi-circle::before  {
        content: ''
      }
    }

    .content {
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background: rgba($color: $prim, $alpha: .3);
      color: #FFF;
      font-size: 2.8em;
      font-weight: 600;
      z-index: 21;
      text-align: center;
      border-radius: 5px;
      padding: 20px;
      max-width: 500px;
      display: flex;
      user-select: none;
    }
  }
}

@media screen and (max-width: 960px){
  .lang {
    display: none !important;
  }

  .Header .v-app-bar {
    padding: 0 !important;
  }

  .logo {
    display: none !important;
  }

  .logo2 {
    position: relative;
    display: block !important;
    top: 18px;
    max-width: 100px !important;
    box-shadow: 3px 3px 5px 0 #0003;
    border-bottom-right-radius: 5px;
    border-bottom-left-radius: 5px;
    z-index: 20;
  }

  .v-list {
    margin-right: 50px;

    .v-list-item {
      font-size: .8em !important;
      width: auto !important;
      white-space: nowrap !important;
      // padding: 0 !important;
    }
  }


  .search {
    display: none !important;
  }
}
</style>
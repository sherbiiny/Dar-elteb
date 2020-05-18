<template>
  <v-carousel cycle class="Carousel" hide-delimiter-background>
    <v-carousel-item v-for="i in carouselItems" :key="i.num">
      <img :src="getImgUrl(i.num)">
      <div class="content">
        {{i.content}}
      </div>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data() {
    return {
      carouselItems: [
        {num: 1, content: "نلتزم بالتميز في تقديم خدمات طبية عالية الجودة"},
        {num: 2, content: "ندرس و نخطط لنبتكر أفضل الخدمات في المجال الطبي"},
        {num: 3, content: "نعمل علي زيادة الفرص الفريدة للاستثمار في المجال الطبي"},
        {num: 4, content: "نعمل علي تخطي التوقعات و تحقيق افضل النتائج"}
      ]
    }
  },

  methods: {
    getImgUrl(pic) {
      let images = require.context('../../assets/img/carousel', false, /\.jpg$/)
      return images('./' + pic + ".jpg")
    }
  },
}
</script>

<style lang="scss">
@import '../../assets/config';

.Carousel {
  height: calc(100vh - 99px) !important;

  .v-responsive {
    height: 100% !important;
    position: relative;

    img {
      width: 100%;
      height: 100%;
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
    font-size: 2.4em;
    font-weight: 400;
    z-index: 21;
    text-align: center;
    border-radius: 5px;
    padding: 20px;
    max-width: 500px;
    display: flex;
    user-select: none;
  }
}

@media screen and (max-width: 960px){

  .Carousel {
    height: 300px !important;

    .v-responsive__content {
      height: 300px !important;
    }

    .content {
      font-size: 1.8em !important;
    }
  }
  
}

@media screen and (max-width: 480px){

  .Carousel {
    height: auto !important;

    .content {
      font-size: 1.2em !important;
    }
  }
  
}
</style>
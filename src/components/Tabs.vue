<template>
  <main class="Tabs">
    <v-container>
      <v-row class="tabs-cont">
        <v-col lg="6" class="col-12">
          <v-tabs color="white">
            <v-tab @click="img = tab.num" class="white--text" v-for="tab in tabs" :key="tab.name">{{tab.name}}</v-tab>
            <v-tab-item class="text-center" v-for="item in items" :key="item.num">
              <h1 v-if="item.title">{{ item.title }}</h1>
              <p v-html="item.content[0]"></p>
              <p v-if="item.content[1]">{{ item.content[1] }}</p>
            </v-tab-item>
          </v-tabs>
          
        </v-col>
        <v-col lg="6" class="col-12">
          <img v-if="img == 1" src="../assets/img/tabs/1.png">
          <img v-if="img == 2" src="../assets/img/tabs/2.png">
          <img v-if="img == 3" src="../assets/img/tabs/3.png">
        </v-col>

      </v-row>

      <div class="sm-container">

        <div class="field">
          <h1>نبذة عن المشروع</h1>
          <img src="../assets/img/tabs/1.png">
          <h4>تقع "مستشفي دار الطب" بمدينة المنصورة</h4>
          <p>ضمن <span>مشروع اندلسية</span> الذي يضم ايضا مجمع سكني مكون من 250 وحدة سكنية و سنتر تجاري ضخم مكون من 150 محل تجاري</p>
        </div>

        <div class="field">
          <h1>مساحة المشروع</h1>
          <img src="../assets/img/tabs/2.png">
          <h4>صمم المشروع علي مسطح مساحته 3000م²</h4>
          <p>روعي فيها الشروط التصميمية الصحية للمستشفيات حيث تضم في هذه المساحة 4 غرف عمليات كبيرة و غرفتان للعمليات المتخصصة</p>
          <p>بالاضافة الي العيادات الخارجية و معامل التحليل و مراكز الاشعة المصممة طبقا لشروط وزارة الصحة</p>
        </div>

        <div class="field">
          <h1>موقع المشروع</h1>
          <img src="../assets/img/tabs/3.png">
          <p>تقع المستشفي علي مجموعة من الطرق الرئيسية أمام كوبري الدراسات بالاتجاه المقابل لمساكن الميناء</p>
          <p>و ذلك لخدمة قطاع عريض من المواطنين حيث يتيح الوصول السريع في حالات الطوارئ و الحالات التي تحتاج الي تدخل جراحي سريع</p>
        </div>
      </div>
    </v-container>
  </main>
</template>

<script>
export default {
  data() {
    return {
      img: 1,

      tabs: [
        {name: "نبذة عن المشروع", num: 1},
        {name: "مساحة المشروع", num: 2},
        {name: "موقع المشروع", num: 3}
      ],
      items: [
        {
          num: 1,
          title: 'تقع "مستشفي دار الطب" بمدينة المنصورة',
          content: [
            `ضمن <span>مشروع اندلسية</span> الذي يضم ايضا مجمع سكني مكون من 250 وحدة سكنية و سنتر تجاري ضخم مكون من 150 محل تجاري`
          ]
        },
        {
          num: 2,
          title: 'صمم المشروع علي مسطح مساحته 3000م²',
          content: [
            "روعي فيها الشروط التصميمية الصحية للمستشفيات حيث تضم في هذه المساحة 4 غرف عمليات كبيرة و غرفتان للعمليات المتخصصة",
            "بالاضافة الي العيادات الخارجية و معامل التحليل و مراكز الاشعة المصممة طبقا لشروط وزارة الصحة"
          ]
        },
        {
          num: 3,
          title: '',
          content: [
            "تقع المستشفي علي مجموعة من الطرق الرئيسية أمام كوبري الدراسات بالاتجاه المقابل لمساكن الميناء",
            "و ذلك لخدمة قطاع عريض من المواطنين حيث يتيح الوصول السريع في حالات الطوارئ و الحالات التي تحتاج الي تدخل جراحي سريع"
          ]
        }
      ]
    }
  },

  methods: {
    getImgUrl(pic) {
      let images = require.context('../assets/img/tabs', false, /\.png$/)
      return images('./' + pic + ".png")
    }
  },
}
</script>

<style lang="scss">
@import '../assets/_config.scss';

.Tabs {
  background: $prim;
  min-height: 460px;
  position: relative;
  z-index: 5;

  .sm-container {
    display: none;
  }

  img {
    max-width: 500px;
  }

  .v-container {
    border-top: 5px solid #000;
  }

  .col {
    padding: 20px !important;
    display: grid;
    align-items: center;
    justify-content: center;
  }

  .v-tabs-bar {
    background: transparent !important;
    color: #FFF !important;
    margin-bottom: 50px;

    .v-tabs-bar__content {
      border-bottom: 1px solid #FFF;
      justify-content: center;
    }

    .v-tab {
      font-size: 1em;
      border: none;
      margin-bottom: -2px;

      &.v-tab--active {
        border: 1px solid #FFF;
        border-bottom: 3px solid $prim;
        border-top-left-radius: 4px;
        border-top-right-radius: 4px;
      }
    }

    .v-tabs-slider {
      display: none !important;
    }
  }

  .theme--light.v-tabs-items {
    background: $prim;
  }

  .v-window {
    min-height: 222px;
  }

  .v-window-item {
    background: $prim !important;
    color: #FFF !important;

    h1 {
      margin-bottom: 30px;
    }

    p {
      line-height: 1.7;
      font-size: 1.2em;
      max-width: 90%;

      span {
        background: #FFF;
        color: $prim;
        display: inline-block;
        font-weight: 600;
        padding: 0 10px;
        height: 32px;
        align-items: center;
        line-height: 28px !important
      }
    }
  }
}

@media screen and (max-width: 600px) {
  .tabs-cont {
    display: none;
  }

  .sm-container {
    display: block !important;
    padding: 10px;
    
    .field {
      text-align: center;
      color: #FFF;
      margin: 80px 0;

      h1 {
        margin-bottom: 20px;
      }

      img {
        max-width: 250px;
        margin: 20px auto;
      }
    }
  }
}

@include MQ($sm) {

}

@include MQ($md) {
  .Tabs {
    padding: 30px;
  }
}

@include MQ($lg) {

}
</style>
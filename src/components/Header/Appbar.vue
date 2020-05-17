<template>
  <nav>
    
    <v-app-bar class="white" elevation="0" height="64px">

      <v-app-bar-nav-icon @click="drawer = !drawer" class="bars"></v-app-bar-nav-icon>

      <v-row>

        <v-col md="10" class="d-flex">
          <div class="search">
            <span>
              <v-icon>fa fa-search</v-icon>
            </span>
            <input type="text" placeholder="بحث...">
          </div>

          <v-list>
            <v-list-item router to='/'>الرئيسية</v-list-item>
            <v-list-item router to='/'>
              خدماتنا
              <v-icon small>fa fa-chevron-down</v-icon>
            </v-list-item>
            <v-list-item router to='/'>من نحن</v-list-item>
            <v-list-item router to='/'>اخر الأخبار</v-list-item>
          </v-list>
        </v-col>

        <v-col md="2">
          <img class="logo2" src="../../assets/img/Logo.jpg">
        </v-col>
      </v-row>


    </v-app-bar>

    <v-navigation-drawer right app v-model="drawer">

      <div class="search">
        <span>
          <v-icon>fa fa-search</v-icon>
        </span>
        <input type="text" placeholder="بحث...">
      </div>

      <v-list>
        <v-list-item router to="/">
          الرئيسية
        </v-list-item>
        <v-list-item router to="/">
          خدماتنا
          <v-icon small>fa fa-chevron-down</v-icon>
        </v-list-item>
        <v-list-item router to="/">
          من نحن
        </v-list-item>
        <v-list-item router to="/">
          اخر الأخبار
        </v-list-item>
      </v-list>

      <div class="number text-center">
        <v-icon>fa fa-phone</v-icon>
        908 566 95 010
      </div>

    </v-navigation-drawer>

  </nav>
</template>

<script>
import $ from 'jquery'

export default {
  data() {
    return {
      drawer: false  
    }
  },

  mounted() {
    $(window).resize(() => {
      if(window.innerWidth > 960) this.drawer = false
    })
  },
}
</script>

<style lang="scss">
@import '../../assets/config';

.v-app-bar {
  position: relative;
  z-index: 6;

  .logo2, .bars {
    display: none;
  }

  .v-list {
    margin: auto;
    height: 100%;
    display: flex;
    align-items: center;

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

.search {
  display: flex;
  align-items: center;

  span {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 30px;
    background: $prim;
    width: 30px;

    i {
      color: #FFF !important;
      font-size: 16px !important;
      cursor: pointer;
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
    height: 30px;
  }
}

.v-navigation-drawer {

  .search {
    padding: 20px;
    margin-top: 50px;
  }

  .v-list {

    .v-list-item {
      padding-right: 60px;
      font-size: 1.3em;
      margin: 20px 0;
      color: #333;
      font-weight: bold;

      &:hover {
        color: $prim !important;
      }

      i {
        margin-right: 10px;
      }

      &::before {
        background: #FFF !important
      }
    }
  }

  .number {
    font-size: 1.2em;
    font-weight: bold;
    position: absolute;
    width: 100%;
    bottom: 20%;
    color: $prim;

    i {
      color: $prim;
      margin-left: 10px;
      transform: rotate(270deg);
    }
  }
}

@media screen and (max-width: 960px){

  .Header .v-app-bar {
    padding: 0 !important;

    .bars {
      display: block;
      margin-right: 20px;
    }

    .logo2 {
      position: absolute;
      display: block !important;
      top: 0;
      left: 10%;
      max-width: 100px !important;
      box-shadow: 3px 3px 5px 0 #0003;
      border-bottom-right-radius: 5px;
      border-bottom-left-radius: 5px;
    }

    .v-list {
      display: none !important;
    }

    .search {
      display: none !important;
    }
  }

}
</style>
<template>
  <v-app>
    <v-content>
      <Header/>
      <Doc/>
      <Tabs/>
    </v-content>
  </v-app>
</template>

<script>
import Header from '@/components/Header/Header'
import Doc from '@/components/Doc'
import Tabs from '@/components/Tabs'
import $ from 'jquery'
import niceScroll from 'jquery.nicescroll'
import AOS from 'aos'
import 'aos/dist/aos.css'

export default {
  name: 'App',

  components: {
    Header,
    Doc,
    Tabs,
  },

  mounted() {
    AOS.init({
      duration: 1000,
      once: true
    })
  }
};
</script>

<style lang="scss">
@import './assets/config';
@import './assets/reset';

@font-face {
  font-family: "DIN Next";
  src: url("./assets/fonts/ArbFONTS-DINNextLTArabic-Regular-2.ttf") format("truetype"),
}
</style>

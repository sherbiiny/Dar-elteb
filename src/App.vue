<template>
  <v-app>
    <v-content>
      <Header/>
      <Doc/>
      <Tabs/>
      <Majors/>
      <Map/>
      <Footer/>
    </v-content>
  </v-app>
</template>

<script>
import Header from '@/components/Header/Header'
import Doc from '@/components/Doc'
import Tabs from '@/components/Tabs'
import Majors from '@/components/Majors'
import Map from '@/components/Map'
import Footer from '@/components/Footer'
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
    Majors,
    Map,
    Footer,
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

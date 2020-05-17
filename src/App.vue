<template>
  <v-app>
    <v-content>
      <Header/>
      <Doc/>
    </v-content>
  </v-app>
</template>

<script>
import Header from '@/components/Header'
import Doc from '@/components/Doc'
import $ from 'jquery'
import niceScroll from 'jquery.nicescroll'
import AOS from 'aos'
import 'aos/dist/aos.css'

export default {
  name: 'App',

  components: {
    Header,
    Doc
  },

  mounted() {
    $('html').niceScroll({
      cursorborder: 'none'
    })

    AOS.init({
      duration: 1000,
      once: true
    })
  }
};
</script>

<style lang="scss">
@import './assets/config';
</style>

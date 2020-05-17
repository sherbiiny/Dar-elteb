<template>
  <header class="Header">

    <Topbar/>
    <Appbar/>
    <Carousel/>

  </header>
</template>

<script>
import Topbar from './Topbar'
import Appbar from './Appbar'
import Carousel from './Carousel'

export default {
  components: {
    Topbar,
    Appbar,
    Carousel
  }
}
</script>
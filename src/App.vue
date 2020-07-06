<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="wrapper" id="home">
      <Nav></Nav>
      <Banner></Banner>
      <LatestAlbum></LatestAlbum>
      <FeaturedAlbum></FeaturedAlbum>
      
      <Footer></Footer>
    </div>
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import Banner from './components/Banner.vue'
import LatestAlbum from './components/LatestAlbum.vue'
import FeaturedAlbum from './components/FeaturedAlbum.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Banner,
    LatestAlbum,
    Footer,
    FeaturedAlbum
  }
}
</script>


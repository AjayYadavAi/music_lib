<template>
  <div id="app">
    <div class="wrapper" id="home">
      <Nav></Nav>
        <router-view></router-view>
      <Footer></Footer>
    </div>
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Footer,
  }
}

</script>


<template>
  <div id="app">
      <Nav/>
      <Main/>
      <Footer/>
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Main,
    Footer
  }
}
</script>

<style lang="scss">
@import './assets/global.scss';
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');

</style>

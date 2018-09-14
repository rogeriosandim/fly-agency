<template>
  <div id="app">
    <Header/>
    <Home/>
    <img alt="Vue logo" src="./assets/imgs/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div>
      <Footer/>
    </div>
  </div>
</template>

<script>
import Header from './pages/Header.vue'
import Home from './pages/Home.vue'
import HelloWorld from './pages/HelloWorld.vue'
import Footer from './pages/Footer.vue'

export default {
  name: 'app',
  components: {
    Header,
    Home,
    HelloWorld,
    Footer
  },
}
</script>

<style lang="scss">

* {
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

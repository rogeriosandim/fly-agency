<template>
  <div id="app">
    <Header/>
    <Home/>
    <img alt="Vue logo" src="./assets/imgs/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Contact/>
    <Footer/>
  </div>
</template>

<script>
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Header from './pages/Header.vue'
import Home from './pages/Home.vue'
import HelloWorld from './pages/HelloWorld.vue'
import Contact from './pages/Contact.vue'
import Footer from './pages/Footer.vue'

Vue.use(BootstrapVue);

export default {
  name: 'app',
  components: {
    Header,
    Home,
    HelloWorld,
    Contact,
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

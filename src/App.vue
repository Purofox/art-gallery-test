<template>
  <div id="app">
    <Header/>
    <Catalog/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import Footer from './components/Footer/Footer.vue'
import Catalog from './components/Catalog/Catalog.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Catalog
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Merriweather:wght@300;400;700&display=swap');

  body {
    background: #F6F3F3;
    color: #343030;
    font-family: 'Merriweather', serif;
    font-size: .729vw;
    margin: 0;
    height: 100%;
    padding: 0;
  }

  html {
    height: 100%;
  }

  a {
    color: #343030;
    text-decoration: none;
  }

  button {
    background: #403432;
    border: 0;
    border-radius: 0;
    color: #fff;
    font-size: .729vw;
    font-weight: 700;
    height: 2.5vw;
    outline: none;
    transition: .3s;
    width: 6.146vw;
  }

  button:hover {
     background: #C1B4B1;
     cursor: pointer;
     transition: .3s;
  }

  #app {
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  .container {
    margin: 0 auto;
    width: 63.333vw;
  }
</style>

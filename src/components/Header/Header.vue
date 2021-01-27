<template>
  <header class="header">
    <div class="container header--container">
      <a href="#" class="logo">
        <img alt="logo" src="../../assets/logo-museum.svg">
      </a>
      <Menu/>
      <Search/>
    </div>
  </header>
</template>

<script>
import Menu from '../Menu/Menu.vue'
import Search from '../Search/Search.vue'

export default {
  name: 'Header',
  components: {
    Menu,
    Search
  }
}
</script>

<style scoped lang="scss" src="./header.scss"></style>
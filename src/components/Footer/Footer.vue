<template>
  <footer class="footer">
    <div class="container footer--container">
      <a href="#" class="logo">
        <img src="../../assets/logo-museum.svg" alt="">
      </a>

      <Menu/>

      <div class="contacts">
        <div class="contacts__item">
          <img src="../../assets/phone.svg" alt=""> +7 (495) 555-55-55
        </div>
        <div class="contacts__item">
          <img src="../../assets/adress.svg" alt=""> г. Москва, ул. Расплетина, 24
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import Menu from '../Menu/Menu.vue'
export default {
name: "Footer",
  components: {
    Menu
  }
}
</script>

<style scoped lang="scss" src="./footer.scss"></style>
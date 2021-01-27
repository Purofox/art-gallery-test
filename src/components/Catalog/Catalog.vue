<template>
  <main class="container">
    <h1>Картины эпохи Возрождения</h1>

    <div class="catalog">
      <Card v-for="(item, i) in goods" :key="i" :index="i" :data="item" @addToCart="onAddToCart"/>
    </div>
  </main>
</template>

<script>
import Card from '../Card/Card.vue'
export default {
  name: "catalog",
  components: {
    Card
  },
  data() {
    return {
      goods: [
        {
          name: '«Рождение Венеры» Сандро Боттичелли',
          oldPrice: 2000000,
          currentPrice: 1000000,
          img: 'img/painting-63186_12801.png',
          available: true,
          added: false,
        },
        {
          name: '«Тайная вечеря»  Леонардо да Винчи',
          currentPrice: 3000000,
          img: 'img/ae973f6678e037cd297053384aa7dca01.png',
          available: true,
          added: false,
        },
        {
          name: '«Сотворение Адама» Микеланджело',
          oldPrice: 6000000,
          currentPrice: 5000000,
          img: 'img/image-191.png',
          available: true,
          added: false,
        },
        {
          name: '«Урок анатомии» Рембрандт',
          img: 'img/201523101423301.png',
          available: false,
          added: false,
        }
      ]
    }
  },
  mounted() {
    if (localStorage.getItem('goods')) {
      this.goods = JSON.parse(localStorage.getItem('goods'));
    }
  },
  methods: {
    onAddToCart (index) {
      this.goods[index].added = true;
      const parsed = JSON.stringify(this.goods);
      localStorage.setItem('goods', parsed);
    }
  }
}
</script>

<style scoped lang="scss" src="./catalog.scss"></style>
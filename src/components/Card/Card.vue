<template>
  <div class="card" :class="{ 'disabled' : !data.available }">
    <div class="card__img">
      <img :src="data.img" alt="">
    </div>
    <div class="card__name">{{data.name}}</div>

    <div class="card__footer" v-if="data.available">
      <div class="card__price">
        <div class="card__old-price" v-if="data.oldPrice">{{data.oldPrice}} $</div>
        <div class="card__current-price" v-if="data.currentPrice">{{data.currentPrice}} $</div>
      </div>
      <button @click="addToCart" :class="{ 'added-cart' : data.added }">
        <span v-if="!this.loader">{{ data.added ? 'В корзине' : 'Купить' }}</span>
        <div v-else class="square"></div>
      </button>
    </div>

    <div class="not-available" v-if="!data.available">Продана на аукционе</div>
  </div>
</template>

<script>
const axios = require('axios');
export default {
  name: "Card",
  props: {
    data: Object,
    index: Number
  },

  data() {
    return {
      loader: false
    }
  },

  methods: {
    addToCart () {
      this.loader = true;
      axios.get('https://jsonplaceholder.typicode.com/posts/1')
        .then(() => {
          this.$emit('addToCart', this.index)
          this.loader = false;
        })
        .catch(() => {
          axios.get('https://reqres.in/api/products/3')
              .then(() => {
                this.$emit('addToCart', this.index)
                this.loader = false;
              })
              .catch((error) => {
                console.log(error)
                this.loader = false;
              });
        });
    }
  }
}
</script>

<style scoped lang="scss" src="./card.scss"></style>
<template>
  <div class="product-box">
    <div class="product-image">
      <img :src="currentProduct.image" alt="">
    </div>
    <div class="product-info">
      <h2 class="product-title">{{ currentProduct.name }}</h2>
      <span class="product-price">€ {{ currentProduct.price }}, 00</span>
      <button btnColor="btn btn-large btn-sucess"
      v-on:click="addProductToCart(currentProduct)">
        Buy Now/Add to Wishlist
      </button>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  components: {
  },

  computed: {
    ...mapGetters({
      currentProduct: 'getCurrentProduct',
    }),
  },

  methods: {
    ...mapActions([
      'addProduct',
      'showOrHiddenModal',
    ]),
    addProductToCart(product) {
      this.addProduct(product);
    },
    rated(rate) {
      return `${rate * 20}%`;
    },
    openModal() {
      this.showOrHiddenModal();
    },
  },

};
</script>

<style scoped>
  .product-box {
    width: 800px;
    height: 400px;
    margin: 50px auto;
    box-sizing: border-box;
    padding: 1.5em;
    background-color: #fff;
    border-radius: 7px;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .product-image {
    width: 300px;
  }

  .product-info {
    width: 400px;
    align-self: flex-start;
  }

  .product-title {
    font-weight: normal;
  }

  .product-price {
    font-size: 2em;
    font-weight: bolder;
  }

  .product-box button {
    width: 300px;
    margin: .3em 0;
  }
</style>

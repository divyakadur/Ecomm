<template>
  <div class="container">
    <Header>
      <router-link to="/checkout">
      <button>
      <span class="btn-circle" v-if="hasProduct()">
           {{ getProductsInCart.length }}
      </span>
      Wishlist
    </button>
      </router-link>
    </Header>
    <transition name="leave">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import Header from './components/Header';

export default {
  components: {
    Header
  },
  methods: {
    ...mapActions([
      'showOrHiddenPopupCart',
    ]),
    hasProduct() {
      return this.getProductsInCart.length > 0;
    },
    showPopupCart() {
      this.showOrHiddenPopupCart();
    },
  },
  computed: {
    ...mapGetters([
      'getProductsInCart',
      'getPopupCart',
    ]),
  },
};
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto');
  body {
    font-family: 'Roboto', sans-serif;
    background-color: #FAFAFA;
  }
button {
  
  background-color: #008CBA; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

  
</style>

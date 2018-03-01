<template>
  <div id="app">
    <Navbar/>
    <div class="container">
      <div class="row">
        <div class="col-sm-9">
          <Inventory @newCartItemAdded="addToCartItem" :items="items"/>
        </div>
        <div class="col-sm-3">
          <Cart @cartItemRemove="removeFromCartItem" :items="cart"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from './components/Navbar'
  import Inventory from './components/Inventory'
  import Cart from './components/Cart'
  import MOCK_DATA from './MOCK_DATA.js'

  export default {
    components: {
      Navbar,
      Inventory,
      Cart
    },
    data() {
      return {
        items: [],
        cart: []
      }
    },
    mounted() {
      this.items = MOCK_DATA
    },
    methods: {
      addToCartItem(item) {
        this.cart.push(item)
      },
      removeFromCartItem(index) {
        this.cart.splice(index, 1)
      }
    }
  }
</script>

<style>
  .row {
    padding-top: 20px;
  }
</style>

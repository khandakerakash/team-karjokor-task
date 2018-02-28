<template>
  <div id="app">
    <Navbar/>
    <div class="container">
      <div class="row">
        <div class="col-sm-9">
          <Inventory :items="items"/>
        </div>
        <div class="col-sm-3">
          <Cart :carts="carts"/>
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
        cats: [ {
          id: 1,
          title: 'test',
          photo: 'http://dummyimage.com/250x250.png/dddddd/000000',
          price: 19.67,
        }]
      }
    },
    mounted() {
      this.items = MOCK_DATA
    }
  }
</script>

<style>
  .row {
    padding-top: 20px;
  }
</style>

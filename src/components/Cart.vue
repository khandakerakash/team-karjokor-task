<template>
  <ul class="list-group">
    <li class="list-group-item">
      <span class="item-name">Name</span>
      <span class="item-price float-right">Price</span>
    </li>
    <hr>
    <li v-for="(cart, index) in carts" :key="index" class="list-group-item">
      <span class="item-name">{{cart.title}}</span>
      <span class="item-price float-right">{{cart.price}}</span>
    </li>
    <hr>
    <li class="list-group-item">
      <span class="item-name">Total</span>
      <span class="item-price float-right">Total Price</span>
    </li>
  </ul>
</template>

<script>
  export default {
    props: ['carts']
  }
</script>

<style>

</style>

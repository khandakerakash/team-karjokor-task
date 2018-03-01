<template>
  <ul class="list-group">
    <li class="list-group-item">
      <span class="item-name">Name</span>
      <span class="item-price float-right">Price</span>
    </li>
    <hr>
    <li v-for="(item, index) in items" :key="index" class="list-group-item">
      <button type="button" class="btn btn-danger btn-sm" @click="removeItem(index)">-</button>
      <span class="item-name">{{(index + 1)}}. {{item.title}}</span>
      <span class="item-price float-right">{{item.price}}</span>
    </li>
    <hr>
    <li class="list-group-item">
      <span class="item-name">Total</span>
      <span class="item-price float-right"><strong>${{totalPrice}}</strong></span>
    </li>
  </ul>
</template>

<script>
  export default {
    props: ['items'],
    computed: {
      totalPrice() {
        let total = 0
        this.items.forEach(item => {
          total += parseFloat(item.price)
        })
        return total.toFixed(2)
      }
    },
    methods: {
      removeItem(index) {
        this.$emit('cartItemRemove', index)
      }
    }
  }
</script>

<style>

</style>

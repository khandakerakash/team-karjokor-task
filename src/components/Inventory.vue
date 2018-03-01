<template>
  <div>
    <div v-for="(item,index) in items" :key="index" class="card">
      <img class="card-img-top" :src="item.photo" :alt="item.title">
      <div class="card-body">
        <h5 class="card-title">{{item.title}}</h5>
        <p>${{item.price}}</p>
        <a @click="addToCart(item)" class="btn btn-success">+ Add</a>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['items'],
    methods: {
      addToCart(item) {
        this.$emit('newCartItemAdded', item)
      }
    }
  }
</script>

<style>
  .card {
    width: 15rem;
    display: inline-block;
    margin-left: 10px;
    margin-bottom: 10px;
  }
</style>

<template>
  <div class="item">
    <div class="item-detail">
      <p><strong>{{ item.name }}</strong></p>
      <p><strong>{{ item.price }}</strong></p>
    </div>
    <button class="button" @click="addToCart(item)">Add to Cart </button>
  </div>

</template>

<script>
export default {
  props: ['item'],
  data() {
    return {}
  },
  methods: {
    addToCart(item) {
      this.$emit('update-cart', item)
    }
  }
}
</script>

<style>
.item {
  display:flex;
  justify-content: space-between;
  width: 80%;
  margin: 10px;
  padding:10px;
  border-radius: 5px;
  border: 1px solid green;
}
.item-detail {
  display: flex;
  justify-content: space-between;
  width: 50%;
}
</style>
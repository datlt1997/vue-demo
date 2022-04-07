<template>
  <div class="item">
    <div class="item-detail">
      <p><strong>{{ total }}</strong></p>
<!--      <p><strong>{{ cart }}</strong></p>-->
    </div>
  </div>

</template>

<script>
export default {
  props: ['total'],
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

</style>
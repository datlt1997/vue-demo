<template>
  <CardComponent :total="total" @empty-cart="emptyCart"/>

  <ItemComponent v-for="item in items" :item="item" :key="item.id" @update-cart="updateCart"/>
</template>

<script setup>
import ItemComponent from './Shop/ItemComponent.vue'
import CardComponent from './Shop/CardComponent.vue'
</script>

<script>
export default {
  data() {
    return {
      items: [
        { id: 111, name: 'banana', price: 12},
        { id: 112, name: 'orange', price: 11},
        { id: 121, name: 'apple', price: 19}
      ],
      // cart: [],
      total: 0
    }
  },
  methods: {
    updateCart(e) {
      // this.cart.push(e);
      this.total++;
    },
    emptyCart() {
      // this.cart = [];
      this.total = 0;
    }
  }
}
</script>

<style>

</style>
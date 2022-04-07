<template>
  <PostContent class="post-item" v-for="name in names" :name="name" />
</template>

<script setup>
import PostContent from './Post/PostContentConponent.vue'
const names = [
    {title: 'nta0', content: 'xzy122'},
    {title: 'nta1', content: 'xzy12'},
    {title: 'nta2', content: 'xzy12'},
]

</script>

<style>
.post-item {
  width:80%;
  background: white;
  border: 1px solid green;
  margin: 10px auto;
  padding: 10px;
  border-radius: 5px;
}
</style>
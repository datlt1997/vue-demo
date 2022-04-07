<template>
<div class="component">
  <p> Name: {{ name.title}} content {{ name.content}}</p>
</div>
</template>
<script>
export default {
  props:['name'],
}
</script>
<style>

</style>
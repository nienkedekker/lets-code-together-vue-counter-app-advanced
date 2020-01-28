<template>
  <ul class="list">
    <li class="item">name: {{ comic.name }}</li>
    <li class="item">premiered: {{ comic.premiered }}</li>
    <li class="item">rating: {{ comic.rating.average }}</li>
    <li class="item">image url: {{ comic.image.medium }}</li>
    <li class="item">read more: {{ comic.url }}</li>
  </ul>
</template>
<script>
  export default {
    props: {
      comic: {
        type: Object,
        default: () => {}
      },
    },
  }
</script>
<style scoped>
  .list {
    background: green;
    border: 1px solid red;
    margin: 5px;
  }

  .item {
    color: pink;
  }
</style>

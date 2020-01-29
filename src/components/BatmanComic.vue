<template>
  <ul>
    <li><img :src="comic.image.medium"></li>
    <li><h2>{{ comic.name }}</h2></li>
    <li>Premiered: {{ comic.premiered }}</li>
    <li>Rating: {{ comic.rating.average }}</li>
    <li>
      <a :href="comic.url">Read More</a>
    </li>
  </ul>
</template>
<script>
  export default {
    name: 'BatmanComic',
    props: {
      comic: {
        type: Object,
        default: () => {}
      }
    },
  }
</script>

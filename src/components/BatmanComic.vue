<template>
  <ul>
    <li>
      <img :src="image" :alt="name">
    </li>
    <li>
      <h2>{{ name }}</h2>
    </li>
    <li>
      Premiered: {{ premiereDate }}
    </li>
    <li>
      Rating: {{ averageRating }}
    </li>
    <li>
      <a :href="url">Read More</a>
    </li>
  </ul>
</template>
<script>
  export default {
    name: 'BatmanComic',
    props: {
      id: {
        type: Number,
        required: true,
      },
      name: {
        type: String,
        required: true,
      },
      url: {
        type: String,
        required: true,
      },
      image: {
        type: String,
        required: true,
      },
      averageRating: {
        type: Number,
        required: true,
      },
      premiereDate: {
        type: String,
        required: true,
      },
    },
  }
</script>
<style>
  ul, li {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
</style>

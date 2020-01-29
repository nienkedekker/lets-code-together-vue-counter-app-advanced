<template>
  <section class="comics-list">
    <batman-comic v-for="comic in batmanComics" :comic="comic.show" :key="comic.show.id" class="single-comic"/>
  </section>
</template>
<script>
import BatmanComic from './BatmanComic.vue';

export default {
  components: {
    BatmanComic,
  },
  props: {
    batmanComics: {
      type: Array,
      default: () => []
    },
  },
}
</script>
<style scoped>
  .comics-list {
    font-family: -apple-system, BlinkMacSystemFont, “Segoe UI”, Roboto, Helvetica, Arial, sans-serif;
  }

  .single-comic {
    color: #282828;
    list-style-type: none;
    text-align: left;
    border: 1px solid #c2c2c2;
    margin: 2em 1em;
    padding: 2em;
    border-radius: .5em;
  }
</style>

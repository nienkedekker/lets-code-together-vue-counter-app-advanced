<template>
  <div id="app">
    <section class="container">
      <h1 class="counter-text">{{ count }}</h1>
      <counter-button @click.native="incrementCount" title="Increment count"/>
      <counter-button @click.native="decrementCount" title="Decrement count"/>
      <counter-button @click.native="resetCount" title="Reset count"/>

      <p v-if="count === 0" class="warning">
        Your count is {{ count }}. Increase your count to see what happens!
      </p>

      <batman-comics v-else :batman-comics="batmanComicsToRender" />
    </section>
  </div>
</template>

<script>
import CounterButton from './components/CounterButton.vue';
import BatmanComics from './components/BatmanComics.vue';

export default {
  name: 'app',
  components: {
    CounterButton,
    BatmanComics
  },
  data() {
    return {
      count: 0,
      batmanShows: [],
    }
  },
  mounted() {
    this.fetchBatmanComics();
  },
  computed: {
    // Why do we need to do this?
    // Try to see what happens when you put `this.batmanShows` directly in our batman-comics component.
    // What show will you see first? Is it the correct show compared to the array we receive from the API?
    batmanComicsToRender() {
      return this.batmanShows.filter((batmanShows, index) => {
        return index < this.count
      });
    }
  },
  methods: {
    incrementCount() {
      this.count = this.count + 1;
    },
    decrementCount() {
      this.count = this.count - 1;
    },
    resetCount() {
      this.count = 0;
    },
    fetchBatmanComics() {
      fetch('https://api.tvmaze.com/search/shows?q=batman')
        .then(response => response.json())
        .then(response => { this.batmanShows = response; })
        // eslint-disable-next-line no-console
        .catch(error => console.log(error))
    },
  }
}
</script>

<style>
  /*
  This is where we'll put our general styling rules.
  They'll serve as a base for all our components.
  For example: the line-height we set here, will 'filter' through to the Button component.
  */

  body, html {
    margin: 0;
    padding: 0;
    color: #212529;
    font-family: 'Courier New', Courier, monospace;
    line-height: 1.5;
    background-color: #faeee7;
  }

  * {
    box-sizing: border-box;
  }

  #app {
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
  }

  .counter-text {
    font-weight: normal;
    font-size: 3rem;
    margin-top: 0;
    margin-bottom: 1.5rem;
  }

  .container {
    width: 100%;
    max-width: 800px;
    padding: 1rem 15px;
    margin: 1em auto;
    background-color: #f8f9fa;
    border: 1px solid rgba(184, 141, 152, 0.38);
    border-radius: 0.25rem;
  }

  .warning {
    background: orange;
  }
</style>

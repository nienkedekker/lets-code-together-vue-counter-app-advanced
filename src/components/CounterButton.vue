<template>
  <button>
    {{ title }}
  </button>
</template>
<script>
  export default {
    props: {
      title: {
        type: String,
        default: 'Click me!'
      },
    },
  }
</script>
<!--
  Scoped means that the styles we define here, are constrained to this component.
  Meaning: they're not global.
  This is cool, because it helps us to avoid styling collisions!
-->
<style scoped>
  button {
    display: inline-block;
    font-weight: bold;
    color: white;
    background-color: #007bff;
    text-align: center;
    vertical-align: middle;
    font-size: 1em;
    padding: .5em 1.2em;
    margin: 1em;
    user-select: none;
    border: 1px solid transparent;
    border-radius: 1em;
    transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  }

  button:active {
    background-color: #0062cc;
    border-color: #005cbf
  }

  button:hover {
    background-color: #0069d9;
    border-color: #0062cc;
    cursor: pointer;
  }
</style>

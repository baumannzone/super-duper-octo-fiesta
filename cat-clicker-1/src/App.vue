<template>
  <div id="app">
    <h1>Cat Clicker</h1>
    <div class="cat-container">
      <cat></cat>
    </div>
  </div>
</template>

<script>
  import Cat from './components/Cat';

  export default {
    name: 'app',
    components: {
      Cat,
    },
  };
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>

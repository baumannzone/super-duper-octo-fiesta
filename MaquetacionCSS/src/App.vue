<template>
  <div id="app" class="container">
    <my-header></my-header>
    <hello></hello>
    <my-footer></my-footer>
  </div>
</template>

<script>
  import MyHeader from './components/MyHeader';
  import Hello from './components/Hello';
  import MyFooter from './components/MyFooter';

  export default {
    name: 'app',
    components: {
      MyHeader,
      Hello,
      MyFooter,
    },
  };
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #444;
  }
</style>

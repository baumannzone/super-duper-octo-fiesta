<template lang="pug">
  #app.container
    my-header
    hello
    my-footer
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

<style lang="stylus">
  // Mixins
  vendor(prop, args)
    -webkit-{prop} args
    -moz-{prop} args
    -ms-{prop} args
    -o-{prop} args
    {prop} args

  transition()
    vendor('transition', arguments)

  #app
    font-family 'Avenir', Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    color #444

</style>

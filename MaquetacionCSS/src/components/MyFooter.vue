<template lang="pug">
  footer
    nav.navbar.fixed-bottom.navbar-light.bg-light
      .navbar.text
        span.badge.badge-info 8 active users

</template>

<script>
  export default {
    name: 'my-footer',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
      };
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>

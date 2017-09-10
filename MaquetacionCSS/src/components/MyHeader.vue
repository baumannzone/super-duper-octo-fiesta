<template lang="pug">
  header
    nav.navbar.navbar-expand-lg.navbar-light.bg-light.fixed-top
      a.navbar-brand(href="#") ACME Ltd.
      button.navbar-toggler(type='button', data-toggle='collapse', data-target='#navbarSupportedContent', aria-controls='navbarSupportedContent', aria-expanded='false', aria-label='Toggle navigation')
        span.navbar-toggler-icon
      .collapse.navbar-collapse.justify-content-end
        .navbar-text Jorge Baumann

</template>

<script>
  export default {
    name: 'hello',
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

<template lang="pug">
  header
    nav.navbar.navbar-expand-lg.navbar-light.bg-light.fixed-top
      a.navbar-brand(href="#") {{ brand }}
      button.navbar-toggler(type='button', data-toggle='collapse', data-target='#myNav', aria-controls='navbarSupportedContent', aria-expanded='false', aria-label='Toggle navigation')
        span.navbar-toggler-icon
      #myNav.collapse.navbar-collapse.justify-content-end
        .navbar-text {{ user }}

</template>

<script>
  export default {
    name: 'my-header',
    data() {
      return {
        brand: 'ACME Ltd.',
        user: 'Jorge Baumann',
      };
    },
  };
</script>

<style></style>

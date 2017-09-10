<template lang="pug">
  footer.navbar.fixed-bottom.navbar-light.bg-light
    .navbar.text
      span.badge.badge-info {{ active }} active users

</template>

<script>
  export default {
    name: 'my-footer',
    data() {
      return {
        active: 8,
      };
    },
  };
</script>

<style></style>

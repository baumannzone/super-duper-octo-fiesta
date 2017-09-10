<template lang="pug">
  .col-sm-6.col-md-4.col-lg-3.d-flex.mb-4
    .card
      .card-body-img( :style="{ backgroundImage: `url('${data.gifurl}')` }" )
      .card-body
        p.card-text {{ data.title }}
      .card-body.d-flex.justify-content-end.align-items-end.pt-0
        a.btn.btn-outline-primary.btn-sm(:href="data.gifurl") Go
</template>

<script>

  export default {
    name: 'card',
    props: {
      data: Object,
    },
  };
</script>


<style lang="stylus">
  // Color
  card-shadow = #DADADA

  .card
    width 100%
    transition box-shadow .15s linear

    &:hover
      box-shadow 0 0 6px 4px card-shadow

    .card-body-img
      min-height 10rem
      background-position center
      background-size cover

</style>

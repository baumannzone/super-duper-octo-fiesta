<template lang="pug">
  .col-sm-6.col-md-4.col-lg-3.d-flex.mb-4
    .card
      .card-body-img( :style="{ backgroundImage: `url('${data.gifurl}')` }" )
      .card-body
        p.card-text {{ data.title }}
      .card-body.d-flex.justify-content-end.align-items-end.pt-0
        a.btn.btn-primary(:href="data.gifurl") Link
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
  .card
    width 100%

    .card-body-img
      min-height 10rem
      background-position center
      background-size cover

</style>

<template lang="pug">
  //.col-md-4.my-card
    .card-wrapper
      img.card-img(:src="data.gifurl")
      p.card-text {{ data.title }}
  .col-sm-6.col-md-4.col-lg-3.d-flex.mb-4
    .card
      img.card-img-top(:src="data.gifurl")
      .card-body
        p.card-text {{ data.title }}
      .card-body.d-flex.justify-content-end.align-items-end
        a.btn.btn-primary(href="#") Link


</template>

<script>

  export default {
    name: 'card',
    props: {
      data: Object,
    },
  };
</script>


<style scoped lang="stylus">
  /*.my-card-cont*/
    /*img*/
      /*max-width 100%*/

</style>

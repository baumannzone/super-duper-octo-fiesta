<template lang="pug">
  .cat
    img(:src="detail.picture.large", @click="increment()")
    p.name {{ fullName }}
    p.click {{ clicks }}

</template>

<script>
  export default {
    name: 'cat',
    props: {
      detail: Object,
    },
    methods: {
      increment( num ) {
        this.detail.clicks += num || 1;
      },
    },
    computed: {
      fullName() {
        return `${this.detail.name.first} ${this.detail.name.last}`;
      },
      clicks() {
        return this.detail.clicks;
      },
    },
  };
</script>

<style lang="stylus">
  .cat
    display block
    margin-top 40px
    padding 5px
    border-bottom 3px solid #fafafa
    &:hover
      cursor pointer

    img
      border-radius 50%

    p.name
      text-transform capitalize

    p.click
      font-weight bolder

</style>

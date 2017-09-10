<template lang="pug">
  .cat
    img(:src="img.large", @click="increment(1)")
    p.name {{ fullName }}
    p.click {{ timesClicked }}

</template>

<script>
  export default {
    name: 'cat',
    props: {
      name: Object,
      img: Object,
      id: Object,
    },
    data() {
      return {
        timesClicked: 0,
      };
    },
    methods: {
      increment( num ) {
        this.timesClicked += num;
      },
    },
    computed: {
      fullName() {
        return `${this.name.first} ${this.name.last}`;
      },
    },
  };
</script>

<style lang="stylus">

  .cat
    margin 0 20px
    color: red
</style>

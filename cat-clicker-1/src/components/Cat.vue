<template>
  <div class="cat">
    <img src="../assets/cat1.jpg" alt="cat" @click="increment(1)">
    <pre> {{ timesClicked }} </pre>
  </div>
</template>

<script>
  export default {
    name: 'cat',
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
  };
</script>

<style scoped>
  img {
    height: 300px;
  }

  pre {
    font-size: 3rem;
  }

</style>

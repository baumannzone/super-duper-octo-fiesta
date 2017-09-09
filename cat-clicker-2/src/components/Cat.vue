<template>
  <div class="cat">
    <img :src="info.url" alt="cat" @click="increment(1)">
    <p class="cat--name">Name: {{ info.name }} </p>
    <pre>Clicks: {{ timesClicked }} </pre>
  </div>
</template>

<script>
  export default {
    name: 'cat',
    props: [
      'info',
    ],
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

  .cat {
    margin: 0 15px;
  }

  img {
    height: 300px;
  }

  img:hover {
    cursor: pointer;
  }

  .cat--name {
    text-transform: capitalize;
  }

  pre {
    font-size: 3rem;
  }

</style>

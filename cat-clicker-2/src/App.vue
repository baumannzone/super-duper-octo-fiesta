<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <h1>{{ msg }}</h1>
    <div class="cat-container">
      <cat :info="cats[0]"></cat>
      <cat :info="cats[1]"></cat>
    </div>
  </div>

</template>

<script>
  import axios from 'axios';
  import Cat from './components/Cat.vue'

  export default {
    name: 'app',
    mounted() {
      axios.get( 'http://jsonplaceholder.typicode.com/photos' )
        .then( res => {
          this.cats = res.data
            .slice( 0, 10 )
            .map( item => {
              item.name = item.title.split( ' ' )[ 0 ];
              delete item.title;
              delete item.albumId;
              delete item.thumbnailUrl;
              return item;
            } );
        } );
    },
    components: {
      Cat,
    },
    data() {
      return {
        msg: 'Cat clicker 2',
        cats: [],
      }
    },
  }
</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1 {
    text-align: center;
  }

  .cat-container {
    display: flex;
    justify-content: center;
  }


</style>

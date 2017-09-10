<template lang="pug">
  .cats
    h1 {{ msg }} [CATS]
    .cat-container
      cat(v-for="(cat, index) in cats",
      :key="index",
      :name="cat.name",
      :img="cat.picture",
      :id="cat.id")

</template>

<script>
  import axios from 'axios';
  import Cat from './Cat';

  export default {
    components: { Cat },
    name: 'cats',
    mounted() {
      axios.get( 'https://randomuser.me/api/?results=5' )
        .then( ( res ) => {
          console.debug( res.data.results );
          this.cats = res.data.results;
        } );
    },
    data() {
      return {
        msg: 'Listado de gatitos',
        cats: null,
      };
    },
  };
</script>

<style lang="stylus">

  .cat-container
    display flex
    justify-content center
    align-items center

</style>

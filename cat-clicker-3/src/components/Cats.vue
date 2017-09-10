<template lang="pug">
  .cats
    template(v-if="loading")
      .spinner
        .bounce1
        .bounce2
        .bounce3
      p Loading..
    ul
      li(v-for="(cat, index) in cats", @click="selectCat(index)")
        h4.name {{ cat.name.first }} {{ cat.name.last }}
    .cat-container
      template(v-if="currentCat === null")
        p Elige un 'gatito'
      template(v-else)
        cat(:detail="catInfo")

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
          this.cats = res.data.results
            .map( ( item ) => {
              item.clicks = 0;
              return item;
            } );
          this.loading = false;
          console.debug( res.data.results );
        } );
    },
    data() {
      return {
        cats: null,
        loading: true,
        catInfo: {},
        currentCat: null,
      };
    },
    methods: {
      selectCat( i ) {
        this.currentCat = i;
        this.catInfo = this.cats[ i ];
      },
    },
  };
</script>

<style lang="stylus">

  ul
    list-style none
    li
      display inline-block
      &:hover
        cursor pointer
        box-shadow 2px 2px 6px #aaa
      h4.name
        padding 0 10px
        text-transform capitalize

  .cat-container
    display flex
    justify-content center
    align-items center

  // Loading effect
  .spinner
    margin 100px auto 0
    width 70px
    text-align center
    & > div
      width 13px
      height 13px
      background-color #666
      border-radius 100%
      display inline-block
      -webkit-animation sk-bouncedelay 1.4s infinite ease-in-out both
      animation sk-bouncedelay 1.4s infinite ease-in-out both
    .bounce1
      animation-delay -0.32s
    .bounce2
      animation-delay -0.16s

  @-webkit-keyframes sk-bouncedelay {
    0%, 80%, 100% {
      -webkit-transform: scale(0)
    }
    40% {
      -webkit-transform: scale(1.0)
    }
  }

  @keyframes sk-bouncedelay {
    0%, 80%, 100% {
      transform: scale(0);
    }
    40% {
      transform: scale(1.0);
    }
  }

</style>

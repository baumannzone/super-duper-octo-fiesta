<template>
  <div class="container">
    <header></header>
    <div class="section-1"></div>
    <div class="section-2"></div>
    <div class="section-3"></div>
  </div>
</template>

<script>
  /* global d3 _ */

  import json from '../data/data.json';

  export default {
    name: 'hello',
    mounted() {
      this.json = json;
      const title = json.msg;
      const coupons = json.coupons;

      // Title
      d3.select( 'header' )
        .append( 'h1' )
        .text( title );

      // Demo
      const data = [ 30, 86, 168, 281, 303, 365 ];
      d3.select( '.section-1' )
        .selectAll( 'div' )
        .data( data )
        .enter()
        .append( 'div' )
        .style( 'width', d => `${d}px` )
        .text( d => d );

      // Section 2
      // Offers by webShop
      const webShops = coupons.map( c => c.webshop_id );
      const counts = {};
      webShops.forEach( ( x ) => {
        counts[ x ] = ( counts[ x ] || 0 ) + 1;
      } );

      d3.select( '.section-2' )
        .selectAll( 'div' );

      console.debug( webShops, counts );

      const lmao = _;
      console.warn( lmao );
    },
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        json: null,
      };
    },
  };
</script>


<style lang="stylus">
  .container
    position relative
    padding 20px
    /*width 800px*/
    background-color #fafafa

  .section-1 div
    font: 10px sans-serif;
    background-color: steelblue;
    text-align: right;
    padding: 3px;
    margin: 1px;
    color: white;

</style>

<template>
  <div class="container">
    <header class="main-title"></header>
    <section class="section-1">
    </section>
    <section class="section-2">
    </section>
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
      d3.select( '.main-title' )
        .append( 'h1' )
        .text( title );

      // Section 1
      // Offers by webShop
      d3.select( '.section-1' )
        .append( 'h3' )
        .text( 'Number of coupons by webShop id' );

      const webShops = coupons.map( c => c.webshop_id );
      const counts = {};
      webShops.forEach( ( x ) => {
        counts[ x ] = ( counts[ x ] || 0 ) + 1;
      } );

      d3.select( '.section-1' )
        .selectAll( 'div' )
        .data( Object.values( counts ) )
        .enter()
        .append( 'div' )
        .style( 'width', d => `${d}%` )
        .text( d => d );

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
    width 600px
    background-color #fafafa

  section
    position relative
    padding 20px 0
    border-top 3px solid #f1f1f1

  .section-1 div,
  .section-2 div
    background-color: #9c27b0;
    text-align: right;
    padding: 6px;
    margin: 2px;
    color: white;

</style>

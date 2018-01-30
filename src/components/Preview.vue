<template>
  <div class="one">
    <ul>
      <li v-for="ticker in ticker">
          <div id="ticker-container" v-for="(name, price_usd) in ticker">
          
          <span class="left">{{price_usd}} =></span>
          <span class="left">{{ name }}</span>
          </div>
      </li>
    </ul>
  </div>
</template>
 

<script>
export default {
  props: [ 'ticker']
}
</script>
<style>
li {
    list-style: none;
    float: left;
    margin: 20px;
}
html{
    background-color: rgb(25, 49, 71);
}
div #ticker-container {
 background-color: #3d4244;
 border: 1px solid rgb(117, 110, 110);
 padding: 2px;
 border-radius: 5px;
 width: 250px;
 box-shadow: 1px 1px rgb(49, 43, 38);
 color: rgb(255, 255, 255);
 font-size: 17px;
 

}
</style>

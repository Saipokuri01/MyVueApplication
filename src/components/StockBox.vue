<template>
    <div>
      <div v-for="stock in stocks" :key="stock._id">
        <SingleStock :stock="stock" />
      </div>
    </div>
  </template>
  
  <script>
  import SingleStock from './SingleStock.vue';
  
  export default {
    name: 'StockBox',
    props: {
      stocks: Array
    },
    components: {
      SingleStock
    }
  };
  </script>
  
  <style scoped>
  div {
    text-align: center;
  }
  </style>
<template>  
  <div class="stock-container">
  <div class="stock-header">
    <span class="label">Stock ID</span>
    <span class="label">Stock Name</span>
    <span class="label">Stock Price($)</span>
    <span class="label">Amount Invested($)</span>
    <span class="label">Profit($)</span>
    <span class="label">Profit Percentage(%)</span>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
  }
};
</script>

<style scoped>
div {
  text-align: center;
}
.stock-header,

.stock-row {
display: contents;
}
.stock-container {
display: grid;
grid-template-rows: auto;
grid-template-columns: repeat(6, 1fr);
text-align: center;
}
.label {
font-weight: bold;
padding: 0.5em;
}
</style>
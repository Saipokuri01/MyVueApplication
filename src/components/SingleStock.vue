<template>
  <div :class="stock.ProfitPercentage >= 0 ? 'green' : 'red'" class="stock-container">
    <div class="stock-row">
      <span>{{ stock.StockID }}</span>
      <span>{{ stock.Name }}</span>
      <span>{{ stock.Price }}</span>
      <span>{{ stock.AmountInvested }}</span>
      <span>{{ stock.Profit }}</span>
      <span>{{ stock.ProfitPercentage }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SingleStock',
  props: {
    stock: Object
  }
};
</script>

<style scoped>
.green {
  background-color: rgb(187, 246, 242);
}

.red {
  background-color: rgb(209, 170, 170);
}

.stock-container {
  display: grid;
  grid-template-rows: auto;
  grid-template-columns: repeat(6, 1fr);
  text-align: center;
}

.stock-header,
.stock-row {
  display: contents;
}

.label {
  font-weight: bold;
  padding: 0.5em;
}

.stock-row span {
  padding: 0.5em;
  font-size: 1em;
  color: rgb(0, 0, 0);
}

div {
  background-color: #ffb89e;
  color: black;
  padding: 1em;
}
</style>

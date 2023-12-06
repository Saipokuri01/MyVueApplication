<template>
   <div class="header-container">
      <h1>My Stock Portfolio</h1>
      <p>By Sai Krishna Pokuri</p>
    </div>
  <div>
    <StockHeader/>
    <StockBox :stocks="stocks" />
  </div>
</template>

<script>
 import StockHeader from '@/components/MyHeader.vue';
import StockBox from '@/components/StockBox.vue';

export default {
  name: 'App',
  components: {
    StockHeader,
    StockBox
  },
  data() {
    return {
      stocks: []
    };
  },
  methods: {
    async fetchStocks() {
      try {
        const res = await fetch('https://myapp-h8il.onrender.com/api');
        if (!res.ok) {
          throw new Error(`Failed to fetch stocks: ${res.statusText}`);
        }
        const data = await res.json();
        return data;
      } catch (error) {
        console.error('Error fetching stocks:', error);
        return [];
      }
    }
  },
  async created() {
    this.stocks = await this.fetchStocks();
  }
};
</script>

<style>
.header-container {
  background-color: rgb(17, 119, 135);
  color: #ecf0f1;
  padding: 1rem;
  text-align: center;
}

.header-container h1 {
  margin: 0;
  color: #fff;
}

.header-container p {
  margin: 0;
  color:#ecf0f1;
}

.app-container {
  padding: 2rem;
}
</style>
<template>
    <div>
      <h2>Products</h2>
      <div class="product-list">
        <div class="product-card" v-for="product in products" :key="product.id">
          <div class="product-details">
            <h3>{{ product.name }}</h3>
            <p>Unit Price: ₱{{ product.price }}</p>
          </div>
          <button @click="addToCart(product.id)">Add to Cart</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { mapState, mapActions } from "vuex";
  export default {
    computed: {
      ...mapState(["products"]),
    },
    methods: {
      ...mapActions(["addToCart"]),
    },
  };
  </script>
  
  <style scoped>
  .product-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
    color: #313131;
  }
  
  .product-card {
    background-color: white;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
  }
  
  .product-card h3 {
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .product-card p {
    font-size: 16px;
    margin-bottom: 15px;
  }
  
  .product-card button {
    padding: 8px 12px;
    font-size: 14px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .product-card button:hover {
    background-color: #0056b3;
  }
  </style>
  
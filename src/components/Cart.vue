<template>
    <div>
      <h2>Shopping Cart</h2>
      <p>Total Items: {{ totalItems }}</p>
      <p>Total Price: ₱{{ totalPrice }}</p>
      <div class="cart-item-list">
        <div class="cart-item-card" v-for="item in cartItems" :key="item.id">
          <div class="cart-item-details">
            <h3>{{ item.name }}</h3>
            <div class="price-container">
              <h1>₱{{ item.price }}</h1>
            </div>
          </div>
          <div class="action-bar">
            <p>Quantity: x{{ item.quantity }}</p>
            <button @click="removeFromCart(item.id)">Remove</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { mapGetters, mapActions } from "vuex";
  export default {
    computed: {
      ...mapGetters(["cartItems", "totalItems", "totalPrice"]),
    },
    methods: {
      ...mapActions(["removeFromCart"]),
    },
  };
  </script>
  
  <style scoped>
  .cart-item-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
    color: #313131;
  }
  
  .cart-item-card {
    background-color: white;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    width: 100%;
  }
  
  .price-container {
    display: flex;
    justify-content: end;
  }
  
  .action-bar {
    display: flex;
    justify-content: space-between;
  }
  
  .cart-item-card h3 {
    font-size: 18px;
    margin-bottom: 5px;
  }
  
  .cart-item-card p {
    font-size: 16px;
    margin-bottom: 5px;
  }
  
  .cart-item-card button {
    padding: 8px 12px;
    font-size: 14px;
    background-color: #dc3545;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .cart-item-card button:hover {
    background-color: #c82333;
  }
  
  .cart-item-details {
    width: 100%;
  }
  </style>
  
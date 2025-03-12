<template>
  <div class="main-content">
    <h1>Vue E-Commerce Store</h1>
    <div class="components">
      <div class="container">
        <ProductList />
      </div>
      <div class="container">
        <Cart />
      </div>
    </div>
  </div>
</template>

<script>
import ProductList from "./components/ProductList.vue";
import Cart from "./components/Cart.vue";

export default {
  components: {
    ProductList,
    Cart,
  },
};
</script>

<style>
.main-content {
  margin-top: 50px;
  width: 100%;
}

.components {
  display: flex;
}

.container {
  width: 50%;
  padding-left: 20px;
  padding-right: 20px;
}

h2,
h1 {
  margin-bottom: 20px;
}
</style>

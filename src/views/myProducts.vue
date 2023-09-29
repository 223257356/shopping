<script>
import ProductItem from '../components/ProductItem.vue'

export default {
  components: {
    ProductItem
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Product A', price: 50 },
        { id: 2, name: 'Product B', price: 150 },
        // ... other products
      ],
      cart: []
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
    }
  }
}
</script>

<template>
    <div class="products">
      <h1>Products</h1>
      <product-item
        v-for="product in products"
        :key="product.id"
        :product="product"
        @add-to-cart="addToCart"
      ></product-item>
    </div>
  </template>

<style>
.products {
  background-color: rgba(248, 248, 248, 0.7);
  padding: 20px;
}

.products p {
  color: #000;
}

</style>

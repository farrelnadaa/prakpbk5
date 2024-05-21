<template>
  <div class="card">
    <img :src="product.image" alt="Product Image">
    <div class="card-content">
      <h3>{{ product.name }}</h3>
      <p>{{ product.description }}</p>
      <p class="price">{{ product.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    product: {
      type: Object,
      required: true
    }
  },
  methods: {
    addToCart() {
      alert(`Added ${this.product.name} to cart!`);
    }
  }
};
</script>

<style scoped>
.card {
  border: 2px solid #ccc;
  padding: 20px;
  border-radius: 8px;
  width: 200px;
  text-align: left;
  background-color: #fff; /* White background for contrast */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s;
}
.card:hover {
  transform: scale(1.05);
}
.card img {
  width: 100%;
  border-radius: 8px;
}
.card-content {
  margin-top: 10px;
}
.card-content h3 {
  margin: 0;
  font-size: 1.2em;
}
.price {
  color: green;
  font-weight: bold;
}
button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}
button:hover {
  background-color: #218838;
}
</style>

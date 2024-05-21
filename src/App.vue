<template>
  <div id="app">
    <Navbar />
    <Carousel />
    <div class="card-container">
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
    <audio controls class="pemutar audio">
      <source src="src/assets/Drake & Lil Baby - Yes Indeed (Lyrics).mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import ProductCard from './components/ProductCard.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    ProductCard,
    Footer
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Nike Air Jordan High', description: 'Brand new in box', price: '$950', image: 'src/assets/51It5HftA2L.webp' },
        { id: 2, name: 'Nike Jordan', description: 'Brand new in box', price: '$200', image: 'src/assets/413B4aZIYtL.webp' },
        { id: 3, name: 'Jordan 3', description: 'Brand new in box', price: '$250', image: 'src/assets/sepatujordan.webp' }
      ]
    };
  }
};
</script>

<style>
#app {
  text-align: center;
  background-color: #000; /* Background color black */
  color: white; /* Ensure text is readable on black background */
  min-height: 100vh; /* Ensure it covers full height */
}

.card-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin: 20px;
}

.audio-player {
  margin-top: 20px;
}
</style>

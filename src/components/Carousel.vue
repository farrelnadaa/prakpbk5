<template>
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div class="carousel-item">
          <img src="src/assets/jordan1000x200.jpg" alt="Carousel 1">
        </div>
        <div class="carousel-item">
          <img src="src/assets/jordan2cr1000x200.jpg" alt="Carousel 2">
        </div>
        <div class="carousel-item">
          <img src="src/assets/jordan3cr1000x200.jpg" alt="Carousel 3">
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Carousel',
    data() {
      return {
        currentIndex: 0
      };
    },
    mounted() {
      this.startCarousel();
    },
    methods: {
      startCarousel() {
        setInterval(() => {
          this.currentIndex = (this.currentIndex + 1) % 3;
        }, 3000);
      }
    }
  };
  </script>
  
  <style scoped>
  .carousel {
    overflow: hidden;
    width: 100%;
    margin: 20px 0;
    position: relative;
  }
  
  .carousel-inner {
    display: flex;
    transition: transform 3s ease;
  }
  
  .carousel-item {
    min-width: 100%;
  }
  
  .carousel-item img {
    width: 100%;
  }
  </style>
  
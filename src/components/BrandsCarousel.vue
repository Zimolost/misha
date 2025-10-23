<template>
  <div class="carousel">
    <div class="track">
      <div class="brand" v-for="(brand, i) in brandsDoubled" :key="i">
        <img :src="brand" alt="brand" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import b1 from '../img/b1.png'
import b2 from '../img/b2.png'
import b3 from '../img/b3.png'
import b4 from '../img/b4.png'
const brands = [b1, b2, b3, b4]
const brandsDoubled = computed(() => [...brands, ...brands])
</script>

<style scoped>
.carousel {
  overflow: hidden;
  background: #bcd5f0;
  padding: 2rem 0;
  /* margin-top: 4rem; */
}

.track {
  display: flex;
  gap: 6rem;
  animation: scroll 25s linear infinite;
}

.brand img {
  height: 100px;
  filter: brightness(85%);
  object-fit: contain;
  /* filter: invert(1); */
}

@keyframes scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50%);
  }
}
</style>

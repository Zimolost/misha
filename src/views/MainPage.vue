<template>
  <HeaderSection />
  <SliderSection />
  <CategoriesSection />
  <BrandsCarousel />
  <TopProducts />
  <AboutSection />
  <ReviewsSection />
  <SubscribeSection />
  <FooterSection />
</template>

<script setup>
import AboutSection from '@/components/AboutSection.vue'
import BrandsCarousel from '@/components/BrandsCarousel.vue'
import CategoriesSection from '@/components/CategoriesSection.vue'
import HeaderSection from '@/components/HeaderSection.vue'
import SliderSection from '@/components/SliderSection.vue'
import TopProducts from '@/components/TopProducts.vue'
import ReviewsSection from '@/components/ReviewsSection.vue'
import SubscribeSection from '@/components/SubscribeSection.vue'
import FooterSection from '@/components/FooterSection.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

* {
  font-family: 'Montserrat';
}
</style>

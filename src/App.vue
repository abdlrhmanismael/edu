<template>
  <div id="app" class="d-flex flex-column min-vh-100">

    <main class="flex-grow-1">
      <HeroSection />
      <FeaturesSection />
      <DashboardSection />
      <ThemesSwiperSection />
      <PromoSection />
      <IntegrationsSwiperSection />
      <TestimonialsSection />

      <PricingSection />


    </main>
 
  </div>
</template>

<script setup>
import HeroSection from './components/sections/HeroSection.vue'
import DashboardSection from './components/sections/DashboardSection.vue'
import FeaturesSection from './components/sections/FeaturesSection.vue'
import PromoSection from './components/sections/PromoSection.vue'
import ThemesSwiperSection from './components/sections/ThemesSwiperSection.vue'
import IntegrationsSwiperSection from './components/sections/IntegrationsSwiperSection.vue'
import TestimonialsSection from './components/sections/TestimonialsSection.vue'
import PricingSection from './components/sections/PricingSection.vue'
</script>

<style>
.min-vh-100 {
  min-height: 100vh;
}
</style>

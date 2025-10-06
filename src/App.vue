<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <main class="">
      <Navbar />
      <Hero />
      <FeatureBar />
      <TopCategories />
      <PopularCourses />

      <PromoBanner />
      <ExploreSkills />
      <Testimonials />
      <LatestArticles />
      <SubscriptionBanner />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from "./components/layout/navbar.vue";
import Hero from "./components/sections/hero.vue";
import FeatureBar from "./components/sections/feature-bar.vue";
import TopCategories from "./components/sections/top-categories.vue";
import PopularCourses from "./components/sections/popular-courses.vue";
import ExploreSkills from "./components/sections/explore-skills.vue";
import PromoBanner from "./components/sections/promo-banner.vue";
import Testimonials from "./components/sections/testimonials.vue";
import LatestArticles from "./components/sections/latest-articles.vue";
import SubscriptionBanner from "./components/sections/subscription-banner.vue";
import Footer from "./components/layout/footer.vue";
</script>

<style>
.min-vh-100 {
  min-height: 100vh;
}
</style>

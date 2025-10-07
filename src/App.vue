<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <main>
      <HeroSection />
      <ProvideSection />
      <TeachersSection />
      <CoursesSection />
      <PrioritySection />
      <ReadyToStartSection />
      <MentorsSection />
    </main>
  </div>
</template>

<script setup>
import HeroSection from "./components/sections/hero.vue";
import PrioritySection from "./components/sections/priority.vue";
import ProvideSection from "./components/sections/provide.vue";
import TeachersSection from "./components/sections/teachers.vue";
import MentorsSection from "./components/sections/mentors.vue";
import CoursesSection from "./components/sections/courses.vue";
import ReadyToStartSection from "./components/sections/ready-to-start.vue";
</script>

<style>
.min-vh-100 {
  min-height: 100vh;
}
</style>

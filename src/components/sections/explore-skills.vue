<template>
  <section class="explore-skills-section mt-5">
    <div class="container">
      <h5 class="text-center mb-5">
        Explore better skills through thousand online courses
      </h5>
      <div class="row">
        <div
          v-for="(skill, index) in skills"
          :key="skill.id"
          class="col-12 col-md-6 col-lg-4 text-center p-4 skill-box"
          :class="{ 'individual-box': skill.isIndividual }"
        >
          <img :src="skill.image" :alt="skill.alt" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from "vue";

// Skills data array
const skills = ref([
  {
    id: 1,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: true,
  },
  {
    id: 2,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: false,
  },
  {
    id: 3,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: true,
  },
  {
    id: 4,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: false,
  },
  {
    id: 5,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: true,
  },
  {
    id: 6,
    image: "/assets/img/theme-four/cap.png",
    alt: "explore skills",
    isIndividual: false,
  },
]);
</script>

<style lang="scss" scoped>
.skill-box {
  transition: all 0.3s ease;
  border-radius: 5px;

  &:hover {
    transform: translateY(-2px);
  }
}

// Individual boxes styling
.individual-box {
  background-color: #f2f3f8;
}
</style>

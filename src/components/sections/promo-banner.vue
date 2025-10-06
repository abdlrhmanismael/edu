<template>
  <section class="promo-banner-section">
    <div class="container">
      <div class="row justify-content-center align-items-center">
        <!-- Centered text content -->
        <div class="col-lg-10 col-md-10 col-12">
          <div class="promo-content">
            <a class="promo-title">
              Make The Most of Your Curiosity To Learn About The World & Access
              An Affordable Education
            </a>
          </div>
        </div>
      </div>

      <!-- Statistics section - Floating circles -->
      <div class="stats-section">
        <div v-for="(stat, index) in allStats" :key="index" class="stat-circle">
          <div class="stat-number">{{ stat.number }}</div>
          <div class="stat-label">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from "vue";

// Statistics data as array of objects
const allStats = ref([
  {
    number: "24k+",
    label: "Students Enrolled",
  },
  {
    number: "17k+",
    label: "Class Completed",
  },
  {
    number: "30k+",
    label: "Learn Growth",
  },
  {
    number: "12k+",
    label: "Top Instructors",
  },
]);
</script>

<style lang="scss" scoped>
.promo-banner-section {
  background: #2563eb;
  background-image: url("/carton.png");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: right center;
  padding: 3rem 0;
  position: relative;
  overflow: hidden;
  height: 60vh;
  display: flex;
  align-items: center;

  // Background pattern
  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #0071dc;
    background-size: 20px 20px;
    background-position: 0 0, 0 10px, 10px -10px, -10px 0px;
    opacity: 0.3;
  }

  // Additional background shapes
  &::after {
    content: "";
    position: absolute;
    top: 20%;
    right: 10%;
    width: 200px;
    height: 100px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    transform: rotate(15deg);
  }
}

.promo-content {
  position: relative;
  z-index: 2;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 60vh;
}

.promo-title {
  color: white;
  font-size: 2.5rem;
  font-weight: mediums;
  line-height: 2.4s;
  margin: 0;
  text-align: center;
  position: relative;
  max-width: 600px;
  margin: 0 auto;
}

.stats-section {
  position: absolute;
  bottom: -75px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
  z-index: 2;
}

.stat-circle {
  background: white;
  border-radius: 50%;
  width: 150px;
  height: 150px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease;
  position: relative;

  &:hover {
    transform: translateY(-5px);
  }
}

.stat-number {
  font-size: 2rem;
  font-weight: bold;
  color: #1a202c;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  color: #6b7280;
  font-weight: 500;
  text-align: center;
  line-height: 1.2;
}

// Responsive Design
@media (max-width: 1200px) {
  .stats-section {
    gap: 1.5rem;
  }

  .stat-circle {
    width: 130px;
    height: 130px;
  }

  .stat-number {
    font-size: 1.8rem;
  }

  .stat-label {
    font-size: 0.8rem;
  }
}

@media (max-width: 991px) {
  .promo-banner-section {
    padding: 3rem 0;
    min-height: 70vh;
  }

  .promo-title {
    font-size: 2rem;
    text-align: center;
    margin-bottom: 2rem;
  }

  .stats-section {
    position: relative;
    bottom: auto;
    margin-top: 3rem;
    justify-content: center;
    gap: 1rem;
  }

  .stat-circle {
    width: 120px;
    height: 120px;
  }

  .stat-number {
    font-size: 1.6rem;
  }

  .stat-label {
    font-size: 0.75rem;
  }
}

@media (max-width: 767px) {
  .promo-title {
    font-size: 1.6rem;
  }

  .stats-section {
    flex-direction: column;
    gap: 1.5rem;
  }

  .stat-circle {
    width: 140px;
    height: 140px;
  }

  .stat-number {
    font-size: 1.8rem;
  }

  .stat-label {
    font-size: 0.85rem;
  }
}

@media (max-width: 575px) {
  .promo-banner-section {
    padding: 2rem 0;
    min-height: 60vh;
  }

  .promo-title {
    font-size: 1.4rem;
  }

  .stat-circle {
    width: 120px;
    height: 120px;
  }

  .stat-number {
    font-size: 1.5rem;
  }

  .stat-label {
    font-size: 0.8rem;
  }
}
</style>

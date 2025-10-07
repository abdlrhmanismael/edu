<template>
  <section class="statistics-banner">
    <!-- Blue Banner Section -->
    <div class="blue-banner">
      <!-- Abstract background shapes -->
      <div class="bg-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
      </div>

      <div class="container">
        <div>
          <!-- Left side - Text content -->
          <div>
            <h2 class="banner-title text-center">
              Make The Most of Your Curiosity To<br />
              Learn About The World & Access An<br />
              Affordable Education
            </h2>
          </div>

          <!-- Right side - Illustration -->
        </div>
      </div>
    </div>

    <!-- White Statistics Section -->
    <div class="statistics-section">
      <div class="circles-statistics">
        <div class="stats-grid">
          <div
            v-for="(stat, index) in statistics.slice(0, 4)"
            :key="index"
            class="stat-card"
          >
            <div class="stat-circle">
              <div class="stat-number">{{ stat.number }}</div>
              <div class="stat-label">{{ stat.label }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Statistic {
  number: string;
  label: string;
}

const statistics: Statistic[] = [
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
];
</script>

<style lang="scss" scoped>
.statistics-banner {
  position: relative;
  overflow: hidden;
}

.blue-banner {
  background: #0071dc;
  background-image: url("/public/static.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  min-height: 50vh;
  padding-bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

// Abstract background shapes
.bg-shapes {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
}

.shape {
  position: absolute;
  background: rgba(255, 255, 255, 0.1);

  &.shape-1 {
    top: 10%;
    left: 5%;
    width: 200px;
    height: 150px;
    transform: rotate(15deg);
    border-radius: 20px;
  }

  &.shape-2 {
    top: 20%;
    right: 10%;
    width: 120px;
    height: 120px;
    transform: rotate(-25deg);
    border-radius: 50%;
  }

  &.shape-3 {
    bottom: 20%;
    left: 15%;
    width: 80px;
    height: 80px;
    transform: rotate(45deg);
    border-radius: 10px;
  }
}

.banner-content {
  position: relative;
  z-index: 3;
  padding: 2rem 0;
}

.banner-title {
  color: white;
  font-size: 2rem;
  list-style: none;
  font-weight: 400;
  line-height: 1.8;
  margin: 0;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  text-decoration: underline;

  text-align: center;
  position: relative;
  z-index: 3;
  display: block;
  width: 100%;
}

.illustration-container {
  position: relative;
  z-index: 3;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 400px;
  padding: 2rem 0;
}

.person-illustration {
  position: relative;
  width: 250px;
  height: 350px;
}

// Person head
.person-head {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 60px;
  z-index: 4;
}

.hair {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 40px;
  background: #2d3748;
  border-radius: 50% 50% 0 0;
}

.face {
  position: absolute;
  top: 15px;
  left: 50%;
  transform: translateX(-50%);
  width: 45px;
  height: 45px;
  background: #fdbcb4;
  border-radius: 50%;

  &::after {
    content: "";
    position: absolute;
    top: 15px;
    left: 50%;
    transform: translateX(-50%);
    width: 8px;
    height: 8px;
    background: #2d3748;
    border-radius: 50%;
  }
}

// Person body
.person-body {
  position: absolute;
  top: 50px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 120px;
  z-index: 3;
}

.shirt {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 70px;
  height: 60px;
  background: #fbbf24; // Mustard yellow
  border-radius: 8px;
}

.pants {
  position: absolute;
  top: 50px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 60px;
  background: #1e40af; // Dark blue
  border-radius: 0 0 8px 8px;
}

// Arms
.arms {
  position: absolute;
  top: 55px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 20px;
  z-index: 2;
}

.arm-left,
.arm-right {
  position: absolute;
  top: 0;
  width: 20px;
  height: 20px;
  background: #fdbcb4;
  border-radius: 10px;
}

.arm-left {
  left: -10px;
}

.arm-right {
  right: -10px;
}

// Laptop
.laptop {
  position: absolute;
  top: 180px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 60px;
  z-index: 2;
}

.laptop-screen {
  position: absolute;
  top: 0;
  left: 0;
  width: 100px;
  height: 40px;
  background: #a78bfa; // Light purple
  border-radius: 4px 4px 0 0;
}

.laptop-keyboard {
  position: absolute;
  top: 35px;
  left: 0;
  width: 100px;
  height: 25px;
  background: #8b5cf6;
  border-radius: 0 0 4px 4px;
}

// Table
.table {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 150px;
  height: 8px;
  z-index: 1;
}

.table-top {
  position: absolute;
  top: 0;
  left: 0;
  width: 150px;
  height: 8px;
  background: #9ca3af; // Light gray
  border-radius: 4px;
}

.table-legs {
  position: absolute;
  top: 8px;
  left: 0;
  width: 150px;
  height: 20px;
}

.leg {
  position: absolute;
  top: 0;
  width: 3px;
  height: 20px;
  background: #6b7280; // Dark gray
}

.leg-left {
  left: 20px;
}

.leg-right {
  right: 20px;
}

// Statistics section
.statistics-section {
  background: white;
  padding: 0;
  position: relative;
  min-height: auto;
  display: flex;
  align-items: flex-start;
  padding-top: 90px;
  padding-bottom: 4rem;

  .circles-statistics {
    position: absolute;
    top: -90px;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 2rem;
}

.stat-card {
  display: flex;
  justify-content: center;
  align-items: center;
  &:nth-child(odd) {
    margin-bottom: 3rem;
  }
}

.stat-circle {
  background: white;
  border-radius: 50%;
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15), 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  z-index: 15;

  &:hover {
    transform: translateY(-8px);
    box-shadow: 0 12px 40px rgba(0, 0, 0, 0.2), 0 6px 20px rgba(0, 0, 0, 0.15);
  }
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: #1e40af;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 1rem;
  color: #6b7280;
  text-align: center;
  font-weight: 500;
  line-height: 1.2;
}

// Responsive Design
@media (max-width: 1200px) {
  .banner-title {
    font-size: 2.5rem;
  }

  .statistics-section {
    padding-top: 80px;
    padding-bottom: 3.5rem;

    .circles-statistics {
      top: -80px;
    }
  }

  .stats-grid {
    gap: 1.5rem;
  }

  .stat-circle {
    width: 160px;
    height: 160px;
  }
}

@media (max-width: 992px) {
  .banner-title {
    font-size: 2rem;
  }

  .statistics-section {
    padding-top: 100px;
    padding-bottom: 3rem;

    .circles-statistics {
      top: -70px;
    }
  }

  .illustration-container {
    height: 300px;
  }

  .person-illustration {
    width: 200px;
    height: 280px;
  }

  .stats-grid {
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
  }
}

@media (max-width: 768px) {
  .blue-banner {
    min-height: 60vh;
  }

  .statistics-section {
    padding: 10rem 0;

    .circles-statistics {
      top: -60px;
    }
  }

  .banner-title {
    font-size: 1.75rem;
    text-align: center;
  }

  .illustration-container {
    height: 250px;
    margin-top: 2rem;
  }

  .person-illustration {
    width: 150px;
    height: 200px;
  }

  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .stat-circle {
    width: 140px;
    height: 140px;
  }

  .stat-number {
    font-size: 2rem;
  }

  .stat-label {
    font-size: 0.9rem;
  }
}

@media (max-width: 576px) {
  .blue-banner {
    min-height: 50vh;
  }

  .statistics-section {
    padding: 10rem;

    .circles-statistics {
      top: -50px;
    }
  }

  .banner-title {
    font-size: 1.5rem;
  }

  .illustration-container {
    height: 200px;
  }

  .person-illustration {
    width: 120px;
    height: 160px;
  }

  .stat-circle {
    width: 120px;
    height: 120px;
  }

  .stat-number {
    font-size: 1.75rem;
  }

  .stat-label {
    font-size: 0.8rem;
  }
}
</style>

<template>
  <section class="top-categories-section">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-8 text-center">
          <h2 class="categories-title mb-5">
            <span class="text-dark-blue">Top </span>
            <span class="text-bright-blue">Categories</span>
          </h2>
        </div>
      </div>
      <div class="row g-4">
        <!-- Categories Section -->
        <div class="col-xl-9 col-lg-8 col-md-12">
          <div class="row g-4">
            <!-- All Category Cards -->
            <div
              v-for="category in categories"
              :key="category.id"
              class="col-xl-4 col-lg-6 col-md-6 col-sm-6"
            >
              <div class="category-card">
                <div class="category-icon me-3">
                  <i :class="category.icon"></i>
                </div>
                <div class="category-text">
                  <span class="text-dark-blue">{{ category.name }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- More Courses Card -->
        <div class="col-xl-3 col-lg-4 col-md-12">
          <div class="more-courses-card text-center">
            <div class="more-courses-icon mb-3">
              <i class="fas fa-play-circle"></i>
            </div>
            <div class="more-courses-text mb-2">
              <span class="course-number">{{ moreCourses.number }}</span>
              <span class="course-text">{{ moreCourses.text }}</span>
            </div>
            <div class="more-courses-link">
              <a href="#" class="text-white text-decoration-none">
                {{ moreCourses.linkText }} →
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Categories data array
const categories = [
  {
    id: 1,
    name: "Mathematics",
    icon: "fas fa-hourglass-half",
  },
  {
    id: 2,
    name: "Idea Generate",
    icon: "fas fa-lightbulb",
  },
  {
    id: 3,
    name: "Chemistry",
    icon: "fas fa-flask",
  },
  {
    id: 4,
    name: "Business Analysis",
    icon: "fas fa-chart-line",
  },
  {
    id: 5,
    name: "Development",
    icon: "fas fa-bug",
  },
  {
    id: 6,
    name: "Email Marketing",
    icon: "fas fa-paper-plane",
  },
];

// More courses data
const moreCourses = {
  number: "2440",
  text: "More Courses",
  linkText: "Get Started",
};
</script>

<style lang="scss" scoped>
.top-categories-section {
  background-color: white;
  padding: 4rem 0;
  position: relative;
  overflow-x: hidden; // Prevent horizontal scroll

  // Background patterns like in the image
  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 30%;
    height: 100%;
    background: linear-gradient(
      45deg,
      transparent 0%,
      rgba(47, 128, 237, 0.05) 25%,
      transparent 50%
    );
    background-size: 20px 20px;
    z-index: 0;
  }

  &::after {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    width: 20%;
    height: 30%;
    background: radial-gradient(
      circle,
      rgba(47, 128, 237, 0.1) 1px,
      transparent 1px
    );
    background-size: 15px 15px;
    z-index: 0;
  }
}

.categories-title {
  font-size: 2.5rem;
  font-weight: bold;
  position: relative;
  z-index: 1;

  .text-dark-blue {
    color: #1a202c !important;
  }

  .text-bright-blue {
    color: #2f80ed !important;
    position: relative;

    &::after {
      content: "";
      position: absolute;
      bottom: -8px;
      left: 0;
      width: 100%;
      height: 4px;
      background: linear-gradient(90deg, #f2c94c 0%, #f2c94c 100%);
      border-radius: 2px;
      transform: skewY(-2deg);
    }
  }
}

.category-card {
  background: #f8f9fa;
  border-radius: 10px;
  padding: 1.5rem;
  display: flex;
  align-items: center;
  transition: all 0.3s ease;
  height: 100%;
  min-height: 80px;
  position: relative;
  z-index: 2;

  &:hover {
    box-shadow: 0 4px 15px rgba(47, 128, 237, 0.15);
    transform: translateY(-2px);
    border-color: #2f80ed;
  }
}

.category-icon {
  width: 50px;
  height: 50px;
  background: #2f80ed;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  color: white;
  flex-shrink: 0;
  position: relative;

  // Yellow background circle - offset to bottom-right
  &::before {
    content: "";
    position: absolute;
    top: 61%;
    left: 58%;
    transform: translate(-50%, -50%);
    width: 50px;
    height: 50px;
    background: #e7ca73;
    border-radius: 50%;
    z-index: -1;
  }
}

.category-text {
  font-size: 1rem;
  font-weight: 500;

  .text-dark-blue {
    color: #1a202c !important;
  }
}

.more-courses-card {
  background: #343a6b;
  border-radius: 10px;
  padding: 2rem 1.5rem;
  box-shadow: 0 4px 15px rgba(52, 58, 107, 0.3);
  transition: all 0.3s ease;
  height: 100%;
  min-height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  z-index: 1;

  &:hover {
    box-shadow: 0 6px 25px rgba(52, 58, 107, 0.4);
    transform: translateY(-2px);
  }
}

.more-courses-icon {
  font-size: 2.5rem;
  color: #2f80ed;
}

.more-courses-text {
  font-size: 1.1rem;
  font-weight: 600;

  .course-number {
    color: #f2c94c;
    font-size: 1.3rem;
    font-weight: bold;
  }

  .course-text {
    color: white;
    margin-left: 0.5rem;
  }
}

.more-courses-link {
  font-size: 0.95rem;

  a {
    color: white;
    &:hover {
      opacity: 0.8;
    }
  }
}

// Extra large screens (1200px+)
@media (min-width: 1200px) {
  .top-categories-section {
    padding: 5rem 0;
  }
}

// Large screens (992px - 1199px)
@media (max-width: 1199px) and (min-width: 992px) {
  .categories-title {
    font-size: 2.2rem;
  }

  .more-courses-card {
    margin-top: 2rem;
  }
}

// Medium screens (768px - 991px)
@media (max-width: 991px) and (min-width: 768px) {
  .categories-title {
    font-size: 2rem;
  }

  .category-card {
    padding: 1.2rem;
    min-height: 70px;
  }

  .more-courses-card {
    padding: 1.5rem;
    min-height: 130px;
    margin-top: 2rem;
  }

  .category-icon {
    width: 45px;
    height: 45px;
    font-size: 1.1rem;

    &::before {
      width: 30px;
      height: 30px;
      top: 60%;
      left: 60%;
    }
  }

  .more-courses-icon {
    font-size: 2rem;
  }
}

// Small screens (576px - 767px)
@media (max-width: 767px) and (min-width: 576px) {
  .categories-title {
    font-size: 1.8rem;
  }

  .category-card {
    padding: 1rem;
    min-height: 65px;
  }

  .more-courses-card {
    padding: 1.2rem;
    min-height: 120px;
    margin-top: 1.5rem;
  }

  .category-icon {
    width: 40px;
    height: 40px;
    font-size: 1rem;

    &::before {
      width: 30px;
      height: 30px;
      top: 60%;
      left: 60%;
    }
  }

  .more-courses-icon {
    font-size: 1.8rem;
  }
}

// Extra small screens (below 576px)
@media (max-width: 575px) {
  .top-categories-section {
    padding: 2rem 0;
    overflow-x: hidden;
    width: 100%;
    max-width: 100vw;
  }

  .container {
    padding-left: 15px;
    padding-right: 15px;
    max-width: 100%;
  }

  .row {
    margin-left: 0;
    margin-right: 0;
  }

  .col-sm-6 {
    padding-left: 8px;
    padding-right: 8px;
  }

  .categories-title {
    font-size: 1.6rem;
    margin-bottom: 2rem !important;
    word-wrap: break-word;
  }

  .category-card,
  .more-courses-card {
    padding: 0.8rem;
    margin-bottom: 1rem;
    max-width: 100%;
    overflow: hidden;
  }

  .category-card {
    min-height: 60px;
  }

  .more-courses-card {
    min-height: 100px;
    margin-top: 1rem;
  }

  .category-icon {
    width: 35px;
    height: 35px;
    font-size: 0.9rem;
    flex-shrink: 0;

    &::before {
      width: 30px;
      height: 30px;
      top: 60%;
      left: 60%;
    }
  }

  .category-text {
    font-size: 0.9rem;
    word-wrap: break-word;
    overflow: hidden;
  }

  .more-courses-icon {
    font-size: 1.5rem;
  }

  .more-courses-text {
    font-size: 1rem;

    .course-number {
      font-size: 1.1rem;
    }
  }
}
</style>

<template>
  <section class="popular-courses-section">
    <div class="container">
      <!-- Header and Filters -->
      <div class="row align-items-center mb-5">
        <div class="col-lg-6">
          <h2 class="section-title">
            <span class="text-dark-blue">Popular </span>
            <span class="text-primary highlighted">Courses</span>
          </h2>
        </div>
        <div class="col-lg-6">
          <div
            class="filter-buttons d-flex flex-wrap gap-2 justify-content-lg-end"
          >
            <button
              v-for="filter in filters"
              :key="filter.id"
              :class="['filter-btn', { active: activeFilter === filter.id }]"
              @click="setActiveFilter(filter.id)"
            >
              {{ filter.name }}
            </button>
          </div>
        </div>
      </div>

      <!-- Course Cards -->
      <div class="row g-4">
        <div
          v-for="course in filteredCourses"
          :key="course.id"
          class="col-xl-3 col-lg-6 col-md-6"
        >
          <div class="course-card">
            <!-- Course Image -->
            <div class="course-image">
              <img :src="course.image" :alt="course.title" class="img-fluid" />
              <!-- Category Tag -->
              <div class="category-tag">
                {{ course.category }}
              </div>
              <!-- Instructor Info -->
              <div class="instructor-info">
                <img
                  :src="course.instructor.avatar"
                  :alt="course.instructor.name"
                  class="instructor-avatar"
                />
                <span class="instructor-name">{{
                  course.instructor.name
                }}</span>
              </div>
            </div>

            <!-- Course Content -->
            <div class="course-content">
              <h3 class="course-title">{{ course.title }}</h3>

              <!-- Course Stats -->
              <div class="course-stats">
                <div class="stat-item">
                  <div class="stat-icon">
                    <i class="fas fa-user"></i>
                  </div>
                  <span>{{ course.students }} Students</span>
                </div>
                <div class="stat-item">
                  <div class="stat-icon star-icon">
                    <i class="fas fa-star"></i>
                  </div>
                  <span>({{ course.rating }}/{{ course.reviews }})</span>
                </div>
              </div>

              <!-- Price and Action -->
              <div class="course-footer">
                <div class="price-section">
                  <span v-if="course.originalPrice" class="original-price">{{
                    course.originalPrice
                  }}</span>
                  <span class="current-price">{{ course.price }}</span>
                </div>
                <button class="explore-btn">Explore Now</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

// Filter buttons data
const filters = [
  { id: "all", name: "All" },
  { id: "cooking", name: "Cooking" },
  { id: "design", name: "Design" },
  { id: "fitness", name: "Fitness" },
  { id: "marketing", name: "Marketing" },
];

// Active filter state
const activeFilter = ref("all");

// Courses data
const courses = ref([
  {
    id: 1,
    title: "Creating Stunning UI Design with Figma",
    category: "DESIGN",
    image: "/hero_one.jpg",
    instructor: {
      name: "Lucas Vaughn",
      avatar: "/person.png",
    },
    students: 9,
    rating: "5.00",
    reviews: 3,
    price: "Free",
    originalPrice: null,
    filterCategory: "design",
  },
  {
    id: 2,
    title: "Building Chatbots with OpenAI's GPT",
    category: "LANGUAGE",
    image: "/hero_two.jpg",
    instructor: {
      name: "Mark Evans",
      avatar: "/person.png",
    },
    students: 2,
    rating: "5.00",
    reviews: 2,
    price: "$29.00",
    originalPrice: "$49.99",
    filterCategory: "marketing",
  },
  {
    id: 3,
    title: "Master the Art of Vegan Cooking Recipes",
    category: "COOKING",
    image: "/hero_three.jpg",
    instructor: {
      name: "David Carter",
      avatar: "/person.png",
    },
    students: 4,
    rating: "5.00",
    reviews: 3,
    price: "$90.00",
    originalPrice: null,
    filterCategory: "cooking",
  },
  {
    id: 4,
    title: "Conversational Spanish for Beginners",
    category: "COOKING",
    image: "/hero_one.jpg",
    instructor: {
      name: "Mark Evans",
      avatar: "/person.png",
    },
    students: 7,
    rating: "5.00",
    reviews: 3,
    price: "$30.00",
    originalPrice: null,
    filterCategory: "cooking",
  },
  {
    id: 5,
    title: "Conversational Spanish for Beginners",
    category: "COOKING",
    image: "/hero_one.jpg",
    instructor: {
      name: "Mark Evans",
      avatar: "/person.png",
    },
    students: 7,
    rating: "5.00",
    reviews: 3,
    price: "$30.00",
    originalPrice: null,
    filterCategory: "cooking",
  },
]);

// Computed property for filtered courses
const filteredCourses = computed(() => {
  if (activeFilter.value === "all") {
    return courses.value;
  }
  return courses.value.filter(
    (course) => course.filterCategory === activeFilter.value
  );
});

// Method to set active filter
const setActiveFilter = (filterId: string) => {
  activeFilter.value = filterId;
};
</script>

<style lang="scss" scoped>
.popular-courses-section {
  background-color: #f8f9fa;
  padding: 4rem 0;
}

.section-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin: 0;

  .text-dark-blue {
    color: #1a202c;
  }

  .highlighted {
    color: #2f80ed;
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

.filter-buttons {
  .filter-btn {
    background: white;
    border: 1px solid #e5e7eb;
    border-radius: 20px;
    padding: 8px 16px;
    font-size: 0.9rem;
    font-weight: 500;
    color: #6b7280;
    transition: all 0.3s ease;
    cursor: pointer;

    &:hover {
      background: #f3f4f6;
      border-color: #d1d5db;
    }

    &.active {
      background: #e5e7eb;
      color: #374151;
      border-color: #d1d5db;
    }
  }
}

.course-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
  transition: all 0.3s ease;
  height: 100%;

  &:hover {
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
    transform: translateY(-2px);
  }
}

.course-image {
  position: relative;
  height: 200px;
  overflow: hidden;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .category-tag {
    position: absolute;
    top: 12px;
    left: 12px;
    background: #2f80ed;
    color: white;
    padding: 4px 8px;
    border-radius: 4px;
    font-size: 0.75rem;
    font-weight: 600;
  }

  .instructor-info {
    position: absolute;
    bottom: 12px;
    left: 12px;
    display: flex;
    align-items: center;
    gap: 8px;

    .instructor-avatar {
      width: 32px;
      height: 32px;
      border-radius: 50%;
      object-fit: cover;
    }

    .instructor-name {
      color: white;
      font-size: 0.85rem;
      font-weight: 500;
      text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
    }
  }
}

.course-content {
  padding: 1.5rem;
}

.course-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #1a202c;
  margin-bottom: 1rem;
  line-height: 1.4;
}

.course-stats {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #e5e7eb;

  .stat-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.85rem;
    color: #6b7280;

    .stat-icon {
      width: 20px;
      height: 20px;
      border: 1px solid #d1d5db;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #f9fafb;

      i {
        font-size: 0.7rem;
        color: #2f80ed;
      }

      &.star-icon {
        i {
          color: #f59e0b;
        }
      }
    }
  }
}

.course-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;

  .price-section {
    .original-price {
      text-decoration: line-through;
      color: #9ca3af;
      font-size: 0.9rem;
      margin-right: 8px;
    }

    .current-price {
      color: #dc2626;
      font-weight: 600;
      font-size: 1rem;
    }
  }

  .explore-btn {
    background: none;
    border: none;
    color: #1a202c;
    font-weight: 500;
    font-size: 0.9rem;
    cursor: pointer;
    transition: color 0.3s ease;

    &:hover {
      color: #2f80ed;
    }
  }
}

// Responsive Design
@media (max-width: 991px) {
  .section-title {
    font-size: 2rem;
    margin-bottom: 1rem;
  }

  .filter-buttons {
    justify-content: flex-start !important;
    margin-top: 1rem;
  }
}

@media (max-width: 767px) {
  .popular-courses-section {
    padding: 3rem 0;
  }

  .section-title {
    font-size: 1.8rem;
  }

  .course-content {
    padding: 1.25rem;
  }

  .course-title {
    font-size: 1rem;
  }
}

@media (max-width: 575px) {
  .section-title {
    font-size: 1.6rem;
  }

  .filter-buttons {
    gap: 0.5rem;

    .filter-btn {
      padding: 6px 12px;
      font-size: 0.8rem;
    }
  }

  .course-content {
    padding: 1rem;
  }

  .course-stats {
    gap: 0.75rem;

    .stat-item {
      font-size: 0.8rem;
    }
  }
}
</style>

<template>
  <section class="courses-section py-5">
    <div class="container">
      <div class="mb-5">
        <h2 class="display-5 fw-bold">Our Recent Courses</h2>
      </div>

      <div class="row g-4">
        <div
          v-for="course in courses"
          :key="course.id"
          class="col-lg-3 col-md-6"
        >
          <div class="card h-100 border-0 rounded-4">
            <div class="position-relative">
              <img :src="course.image" class="card-img-top" alt="Course" />
              <span
                class="badge position-absolute top-0 start-0 m-3"
                :class="course.badgeClass"
              >
                {{ course.category }}
              </span>
            </div>
            <div class="card-body">
              <div class="d-flex align-items-center mb-3">
                <img
                  :src="course.instructor.image"
                  class="rounded-circle me-2"
                  width="30"
                  height="30"
                  alt="Instructor"
                />
                <small class="text-muted">{{ course.instructor.name }}</small>
              </div>
              <h5 class="card-title">{{ course.title }}</h5>
              <div class="d-flex align-items-center mb-3">
                <small class="text-muted me-3">
                  👤 {{ course.students }} Students
                </small>
                <small class="text-warning">
                  ⭐ ({{ course.rating.score }}/{{ course.rating.reviews }})
                </small>
              </div>
              <div class="d-flex justify-content-between align-items-center">
                <div v-if="course.price.original">
                  <span class="text-muted text-decoration-line-through me-2">
                    ${{ course.price.original }}
                  </span>
                  <span class="text-danger fw-bold">
                    ${{ course.price.current }}
                  </span>
                </div>
                <span
                  v-else-if="course.price.current === 0"
                  class="text-danger fw-bold"
                >
                  Free
                </span>
                <span v-else class="text-danger fw-bold">
                  ${{ course.price.current }}
                </span>
                <a href="#" class="btn btn-sm"> Explore Now </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const courses = ref([
  {
    id: 1,
    title: "Mastering Responsive Web Design Techniques",
    category: "DEVELOPMENT",
    badgeClass: "custom-badge",
    image: "/public/recent cources background.png",
    instructor: {
      name: "David Carter",
      image: "/public/person.png",
    },
    students: 11,
    rating: {
      score: "5.00",
      reviews: 3,
    },
    price: {
      current: 0,
      original: null,
    },
  },
  {
    id: 2,
    title: "Building Chatbots with OpenAI's GPT",
    category: "LANGUAGE",
    badgeClass: "custom-badge",
    image: "/public/person.png",
    instructor: {
      name: "Mark Evans",
      image: "/public/person.png",
    },
    students: 2,
    rating: {
      score: "5.00",
      reviews: 2,
    },
    price: {
      current: "29.00",
      original: "49.99",
    },
  },
  {
    id: 3,
    title: "Master the Art of Vegan Cooking Recipes",
    category: "COOKING",
    badgeClass: "custom-badge",
    image: "/public/recent cources background.png",
    instructor: {
      name: "David Carter",
      image: "/public/person.png",
    },
    students: 4,
    rating: {
      score: "5.00",
      reviews: 3,
    },
    price: {
      current: "90.00",
      original: null,
    },
  },
  {
    id: 4,
    title: "Introduction to Python for Web Developers",
    category: "DEVELOPMENT",
    badgeClass: "custom-badge",
    image: "/public/recent cources background.png",
    instructor: {
      name: "David Carter",
      image: "/public/person.png",
    },
    students: 3,
    rating: {
      score: "5.00",
      reviews: 2,
    },
    price: {
      current: "49.00",
      original: null,
    },
  },
]);
</script>

<style scoped>
.courses-section {
  background-color: #ebf2ff;
  background-image: url("/public/recent\ cources\ background.png");
  background-repeat: no-repeat;
  background-position: center;
}
.card {
  transition: transform 0.2s;
}

.card:hover {
  transform: translateY(-5px);
}

.card-img-top {
  height: 200px;
  object-fit: cover;
}

.custom-badge {
  background-color: #1cb098 !important;
  color: white;
}
</style>

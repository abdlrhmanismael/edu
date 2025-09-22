<template>
  <section class="features-section py-5">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <div class="features-header text-center mb-5 position-relative">
            <h2 class="features-title fs-4 fw-semibold text-primary mb-3">Our Features</h2>
            <p class="features-subtitle display-5 fw-bold text-dark mb-0">Fostering a playful & engaging learning environment</p>
          </div>
        </div>
      </div>
      
      <div class="row g-4">
        <div 
          v-for="feature in features" 
          :key="feature.id"
          class="col-lg-3 col-md-6"
        >
          <div class="feature-card card h-100 border-1" @mouseenter="hoveredCard = feature.id" @mouseleave="hoveredCard = null">
            <div class="card-body p-4">
              <div class="d-flex align-items-center gap-2 mb-3">
                <div class="feature-icon bg-light rounded-3 p-3 d-flex align-items-center justify-content-center">
                  <i :class="feature.icon" class="feature-icon-text"></i>
                </div>
                <h3 class="feature-title card-title h5 fw-bold text-dark mb-0">{{ feature.title }}</h3>
              </div>
              <p class="feature-description card-text text-muted mb-3 lh-base">{{ feature.description }}</p>
              <a href="#" class="feature-link text-decoration-none d-inline-flex align-items-center gap-2 fw-semibold text-primary">
                Start now <i class="fas fa-chevron-right small"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'

const hoveredCard = ref<number | null>(null)

const features = reactive([
  {
    id: 1,
    icon: 'fas fa-desktop',
    title: 'All-in-One Learning System',
    description: 'Everything you need to manage content, classes, and students in one place.'
  },
  {
    id: 2,
    icon: 'fas fa-users',
    title: 'Class & Student Management',
    description: 'Full control over student enrollment, attendance tracking, and class scheduling.'
  },
  {
    id: 3,
    icon: 'fas fa-video',
    title: 'Video Conferencing Integration',
    description: 'Connect seamlessly with Zoom and other platforms for live sessions.'
  },
  {
    id: 4,
    icon: 'fas fa-globe',
    title: 'Custom Domain',
    description: 'Give your academy a unique and professional identity with your own website address.'
  },
  {
    id: 5,
    icon: 'fas fa-brain',
    title: 'AI-Powered Support',
    description: 'Use smart tools to speed up content creation, improve the learning experience.'
  },
  {
    id: 6,
    icon: 'fas fa-clipboard-check',
    title: 'Comprehensive Testing System',
    description: 'Create interactive quizzes, automate grading, and access detailed performance reports.'
  },
  {
    id: 7,
    icon: 'fas fa-chart-line',
    title: 'Educational Management',
    description: 'Manage everything—students, classes, content, tests, and reports—from a single platform.'
  },
  {
    id: 8,
    icon: 'fas fa-palette',
    title: 'Customizable Themes',
    description: 'Easily switch between professional templates to match your academy\'s brand and style.'
  }
])
</script>

<style scoped>
.feature-card {
  border-radius: 16px;
  transition: all 0.3s ease;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.feature-card:hover {
  background: #013488 !important;
  transform: translateY(-5px);
}

.feature-icon-text {
  font-size: 1rem;
  color: #3963a6;
  transition: all 0.3s ease;
}


.feature-card:hover .feature-title {
  color: white !important;
}

.feature-card:hover .feature-description {
  color: rgba(255, 255, 255, 0.9) !important;
}

.feature-card:hover .feature-link {
  color: white !important;
}

.feature-link i {
  transition: transform 0.3s ease;
}

.feature-card:hover .feature-link i {
  transform: translateX(3px);
}

/* Responsive Design */
@media (max-width: 768px) {
  .feature-icon-text {
    font-size: 1.75rem;
  }
}
</style>

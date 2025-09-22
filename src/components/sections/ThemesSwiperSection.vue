<template>
  <section class="themes-swiper-section bg-white py-5 overflow-hidden">
    <div class="container-fluid px-4">
      <div class="row">
        <div class="col-12">
          <div class="section-header  mb-5">
            <h2 class="section-title display-5 fw-bold text-dark mb-3 lh-sm">Customizable Themes for Your Academy</h2>
            <p class="section-description fs-4 text-muted lh-base">
              Choose from a variety of professional templates and easily adjust colors, fonts, and layouts to match your brand identity. Design your academy's website exactly the way you want—without writing a single line of code.
            </p>
          </div>
        </div>
      </div>
      
      <div class="row">
        <div class="col-12">
          <swiper
            :modules="modules"
            :slides-per-view="1"
            :space-between="30"
            :breakpoints="{
              768: {
                slidesPerView: 2,
                spaceBetween: 30
              },
              1024: {
                slidesPerView: 3,
                spaceBetween: 40
              }
            }"
            class="themes-swiper py-4"
          >
            <swiper-slide v-for="theme in themes" :key="theme.id" class="theme-slide h-auto">
              <div class="theme-card card h-100 border-0 shadow-sm" @mouseenter="showTrialOverlay = theme.id" @mouseleave="showTrialOverlay = null">
                <div class="theme-image-container position-relative overflow-hidden rounded-4">
                  <img :src="theme.image" :alt="theme.name" class="theme-image w-100 h-100 object-fit-cover" />
                  
                  <!-- Hover Overlay with Trial Layout -->
                  <div 
                    class="trial-overlay position-absolute top-0 start-0 w-100 h-100 d-flex align-items-center justify-content-center" 
                    :class="{ 'show': showTrialOverlay === theme.id }"
                  >
                    <div class="trial-content text-center text-white p-4">
                      <div class="trial-cta">
                        <Button variant="primary" size="lg" class="me-3">
                          Start Free Trial
                        </Button>
                      </div>
                    </div>
                  </div>
                </div>
                
                <div class="theme-name-container card-body text-center bg-white p-4">
                  <h3 class="theme-name card-title h5 fw-semibold text-dark mb-0">{{ theme.name }}</h3>
                </div>
              </div>
            </swiper-slide>
          </swiper>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination, Navigation } from 'swiper/modules'

// Import Swiper styles
import 'swiper/css'
import Button from '../ui/Button.vue'


const modules = [Pagination, Navigation]

const showTrialOverlay = ref<number | null>(null)

const themes = ref([
  {
    id: 1,
    name: 'Languages',
    image: '/theme.png',
    description: 'Perfect for language learning academies with multilingual support',
    features: [
      'Multi-language support',
      'Interactive lessons',
      'Progress tracking',
      'Certificate generation'
    ]
  },
  {
    id: 2,
    name: 'Arabic',
    image: '/theme.png',
    description: 'Designed specifically for Arabic and Quran learning institutions',
    features: [
      'Arabic text support',
      'Quran study tools',
      'Islamic calendar',
      'Prayer time integration'
    ]
  },
  {
    id: 3,
    name: 'Math',
    image: '/theme.png',
    description: 'Engaging math learning platform with interactive tools',
    features: [
      'Interactive calculators',
      'Step-by-step solutions',
      'Math games',
      'Progress analytics'
    ]
  },
  {
    id: 4,
    name: 'Science',
    image: '/theme.png',
    description: 'Comprehensive science education platform',
    features: [
      'Virtual labs',
      '3D models',
      'Experiment simulations',
      'Scientific calculators'
    ]
  },
  {
    id: 5,
    name: 'Arts',
    image: '/theme.png',
    description: 'Creative arts and design learning environment',
    features: [
      'Portfolio galleries',
      'Design tools',
      'Creative challenges',
      'Art history timeline'
    ]
  },
  {
    id: 6,
    name: 'Business',
    image: '/theme.png',
    description: 'Professional business and entrepreneurship courses',
    features: [
      'Case studies',
      'Business simulations',
      'Networking tools',
      'Industry insights'
    ]
  }
])
</script>

<style scoped>
.theme-card {
  border-radius: 20px;
  transition: all 0.3s ease;
}

.theme-card:hover {
  transform: translateY(-10px);
}

.theme-image-container {
  height: 700px;
}

.theme-image {
  transition: transform 0.3s ease;
}

.theme-card:hover .theme-image {
  transform: scale(1.05);
}

.trial-overlay {
  background: rgba(0, 0, 0, 0.3);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}

.trial-overlay.show {
  opacity: 1;
  visibility: visible;
}

.trial-content {
  max-width: 280px;
}

/* Swiper Navigation Styles */
:deep(.swiper-button-next),
:deep(.swiper-button-prev) {
  color: #1976d2;
  background: white;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

:deep(.swiper-button-next:hover),
:deep(.swiper-button-prev:hover) {
  background: #1976d2;
  color: white;
  transform: scale(1.1);
}

:deep(.swiper-button-next::after),
:deep(.swiper-button-prev::after) {
  font-size: 18px;
  font-weight: bold;
}

:deep(.swiper-pagination-bullet) {
  background: #ccc;
  opacity: 1;
  width: 12px;
  height: 12px;
}

:deep(.swiper-pagination-bullet-active) {
  background: #1976d2;
}

/* Responsive Design */
@media (max-width: 768px) {
  .theme-image-container {
    height: 350px;
  }
  
  .trial-content {
    padding: 1.5rem;
    max-width: 250px;
  }
}

@media (max-width: 576px) {
  .theme-image-container {
    height: 300px;
  }
  
  .trial-content {
    padding: 1rem;
    max-width: 220px;
  }
}
</style>

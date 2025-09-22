<template>
  <section class="dashboard-section bg-white py-5 min-vh-80 d-flex align-items-center">
    <div class="container">
      <div class="row align-items-center">
        <!-- Left Column - Dashboard Mockup -->
        <div class="col-lg-6 col-md-12 mb-5 mb-lg-0">
          <div class="dashboard-mockup position-relative d-flex justify-content-center align-items-center">
            <!-- Dashboard Image -->
            <div class="image-container position-relative">
              <img 
                src="/website-preview.png" 
                alt="Dashboard Preview" 
                class="dashboard-image w-100 rounded-4 shadow-lg"
              />
            </div>
          </div>
        </div>
        
        <!-- Right Column - Marketing Content -->
        <div class="col-lg-6 col-md-12">
          <div class="marketing-content py-4">
            <h1 class="marketing-title fw-1 fw-bold text-dark mb-4 lh-sm">
              All the Features You Need in One Dashboard
            </h1>
            <p class="marketing-description fs-5 text-muted mb-4 lh-base">
              Manage your entire academy from a single, powerful dashboard. From classes and students to exams, AI tools, and integrations — everything is just a click away.
            </p>
            <Button variant="primary" size="lg" class="me-3">
              Start now!
            </Button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import Button from '../ui/Button.vue';

// No reactive data needed for this static showcase section
</script>

<style scoped>
.dashboard-mockup {
  min-height: 500px;
}

.dashboard-mockup::before {
  content: '';
  position: absolute;
  top: 20px;
  left: 20px;
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%);
  border-radius: 20px;
  z-index: 1;
}

.dashboard-mockup::after {
  content: '';
  position: absolute;
  bottom: 20px;
  right: 20px;
  width: 150px;
  height: 150px;
  background: linear-gradient(135deg, #f3e5f5 0%, #e1bee7 100%);
  border-radius: 20px;
  z-index: 1;
}

.image-container {
  z-index: 2;
}

.dashboard-image {
  max-width: 500px;
  height: auto;
  transition: transform 0.3s ease;
}

.dashboard-image:hover {
  transform: translateY(-5px);
}

/* Responsive Design */
@media (max-width: 768px) {
  .dashboard-mockup {
    min-height: 400px;
  }
  
  .dashboard-mockup::before {
    width: 150px;
    height: 150px;
    top: 15px;
    left: 15px;
  }
  
  .dashboard-mockup::after {
    width: 120px;
    height: 120px;
    bottom: 15px;
    right: 15px;
  }
}

@media (max-width: 576px) {
  .dashboard-mockup::before {
    width: 120px;
    height: 120px;
    top: 10px;
    left: 10px;
  }
  
  .dashboard-mockup::after {
    width: 100px;
    height: 100px;
    bottom: 10px;
    right: 10px;
  }
}
</style>

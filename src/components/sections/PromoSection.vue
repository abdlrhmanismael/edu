<template>
  <section class="py-5 bg-white">
    <div class="container">
      <div class="row align-items-center">
        <!-- Left Side - Website Preview Image -->
        <div class="col-lg-6 col-md-12 mb-4 mb-lg-0">
          <div class="image-container">
            <img src="/website-preview.png" alt="Website Preview" class="preview-image" />
          </div>
        </div>
        
        <!-- Right Side - Promotional Content -->
        <div class="col-lg-6 col-md-12">
          <div class="py-4">
            <h1 class="display-5 fw-medium text-dark mb-4">Discover What's Possible</h1>
            
            <div class="mb-5">
              <div class="d-flex align-items-start mb-4">
                <div class="feature-icon">
                  <i class="fas fa-th"></i>
                </div>
                <p class="fs-5 text-muted mb-0 ms-3">Explore seamless integration with Zoom for live classes.</p>
              </div>
              
              <div class="d-flex align-items-start mb-4">
                <div class="feature-icon">
                  <i class="fas fa-file-alt"></i>
                </div>
                <p class="fs-5 text-muted mb-0 ms-3">Try the powerful student and exam management system.</p>
              </div>
              
              <div class="d-flex align-items-start mb-4">
                <div class="feature-icon">
                  <i class="fas fa-users"></i>
                </div>
                <p class="fs-5 text-muted mb-0 ms-3">Manage your educational meetings easily with Zoom.</p>
              </div>
            </div>
            
            <div>
              <Button variant="primary" size="lg">
                Start now!
              </Button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import Button from '../ui/Button.vue'
</script>

<style scoped>
.image-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 60px;
  overflow: visible;
}

.image-container::before {
  content: '';
  position: absolute;
  width: 120px;
  height: 120px;
  background: linear-gradient(45deg, #1976d2, #42a5f5);
  border-radius: 50%;
  top: 20px;
  right: 20px;
  opacity: 0.7;
  animation: float 6s ease-in-out infinite;
}

.image-container::after {
  content: '';
  position: absolute;
  width: 100px;
  height: 100px;
  background: linear-gradient(45deg, #e91e63, #f48fb1);
  border-radius: 50%;
  bottom: 20px;
  left: 20px;
  opacity: 0.7;
  animation: float 8s ease-in-out infinite reverse;
}

.preview-image {
  width: 100%;
  max-width: 500px;
  height: auto;
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  position: relative;
  z-index: 1;
}

.preview-image:hover {
  transform: scale(1.02);
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

.feature-icon {
  background: #1976d2;
  color: white;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  font-size: 1.1rem;
}

/* Responsive Design */
@media (max-width: 992px) {
  .preview-image {
    max-width: 400px;
  }
  
  .image-container {
    padding: 50px;
  }
  
  .image-container::before {
    width: 100px;
    height: 100px;
    top: 15px;
    right: 15px;
  }
  
  .image-container::after {
    width: 80px;
    height: 80px;
    bottom: 15px;
    left: 15px;
  }
}

@media (max-width: 768px) {
  .preview-image {
    max-width: 350px;
  }
  
  .image-container {
    padding: 40px;
  }
  
  .image-container::before {
    width: 80px;
    height: 80px;
    top: 10px;
    right: 10px;
  }
  
  .image-container::after {
    width: 60px;
    height: 60px;
    bottom: 10px;
    left: 10px;
  }
}

@media (max-width: 576px) {
  .preview-image {
    max-width: 300px;
  }
  
  .image-container {
    padding: 30px;
  }
  
  .image-container::before {
    width: 60px;
    height: 60px;
    top: 5px;
    right: 5px;
  }
  
  .image-container::after {
    width: 50px;
    height: 50px;
    bottom: 5px;
    left: 5px;
  }
}
</style>

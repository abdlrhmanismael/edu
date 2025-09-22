  <template>
    <section class="hero-section">
      <div class="container-fluid px-5">
        <div class="row align-items-center min-vh-100">
        <!-- Left Side - Text Content -->
        <div class="col-lg-6">
          <div class="hero-content position-relative z-2 py-5">
            <h1 class="hero-title display-1 fw-bold lh-sm mb-4 ">
              {{ heroData.title }}
            </h1>
            
            <p class="hero-description fs-3 text-muted mb-4 lh-base">
              {{ heroData.description }}
            </p>
            
            <div class="hero-actions mb-5">
              <Button variant="primary" size="lg" class="me-3">
                {{ heroData.buttonText }}
              </Button>
            </div>
          </div>
        </div>
        
         <!-- Right Side - Visual Content -->
         <div class="col-lg-6">
           <div class="hero-visual position-relative py-5">
             <div class="visual-frame bg-white rounded-4 shadow-lg overflow-visible p-2">
               <!-- Website Preview Image -->
               <img 
                 :src="websitePreviewData.src" 
                 :alt="websitePreviewData.alt" 
                 class="website-preview-image w-100 rounded-4"
               />
               
               <!-- Hex Code Card -->
               <div class="hex-card card d-none d-md-block position-absolute bg-white bg-opacity-75 rounded-3 p-3  border-0 shadow-none">
                 <div class="card-body p-0">
                   <div class="hex-title d-flex justify-content-between align-items-center mb-2">
                     <p class="mb-0 fw-semibold text-dark">{{ hexData.title }}</p>
                     <div class="inline-color-swatch d-inline-flex align-items-center gap-2 bg-light rounded-pill px-3 py-1">
                       <div class="color-circle rounded-circle border" style="background-color: #1708FF; width: 16px; height: 16px;"></div>
                       <span class="hex-code fw-medium text-dark font-monospace">#1708FF</span>
                     </div>
                   </div>
                   <div class="color-swatches d-flex flex-column gap-2">
                     <div 
                       v-for="(swatch, index) in hexData.colorSwatches" 
                       :key="index"
                       class="color-swatch d-flex align-items-center gap-3 cursor-pointer"
                     >
                       <div 
                         class="color-circle rounded-circle flex-shrink-0" 
                         :style="{ backgroundColor: swatch.color, width: '12px', height: '12px' }"
                       ></div>
                       <span class="hex-code fw-medium text-muted font-monospace small">{{ swatch.hexCode }}</span>
                     </div>
                   </div>
                 </div>
               </div>
               
               <!-- Congratulations Notification -->
               <div class="congratulations-card card d-none d-md-block position-absolute bg-white rounded-3 p-3 border-0 shadow-none">
                 <div class="card-body d-flex align-items-center gap-3 p-0">
                   <div class="congratulations-icon bg-warning text-white rounded-2 d-flex align-items-center justify-content-center flex-shrink-0" style="width: 24px; height: 24px;">
                     {{ congratulationsData.icon }}
                   </div>
                   <div class="congratulations-content flex-grow-1">
                     <div class="congratulations-title fw-bold text-dark mb-1">{{ congratulationsData.title }}</div>
                     <div class="congratulations-text text-muted">{{ congratulationsData.text }}</div>
                   </div>
                   <div class="congratulations-checkmark flex-shrink-0">{{ congratulationsData.checkmark }}</div>
                 </div>
               </div>
             </div>
           </div>
         </div>
        </div>
      </div>
    </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue';
import Button from '../ui/Button.vue';

// Hero content data
const heroData = reactive({
  title: "Build your academy's perfect website in minutes",
  description: "Build your academy's perfect website in minutes",
  buttonText: "Join for free"
});

// Hex card data
const hexData = reactive({
  title: "Hex",
  colorSwatches: [
    { color: "#FFD700", hexCode: "#FFD700" },
    { color: "#FF6B35", hexCode: "#FF6B35" },
    { color: "#E91E63", hexCode: "#E91E63" },
    { color: "#9C27B0", hexCode: "#9C27B0" },
    { color: "#2196F3", hexCode: "#2196F3" },
    { color: "#1708FF", hexCode: "#1708FF" }
  ]
});

// Congratulations card data
const congratulationsData = reactive({
  icon: "📧",
  title: "Congratulations",
  text: "Your website is ready",
  checkmark: "✅"
});

// Website preview data
const websitePreviewData = reactive({
  src: "/website-preview.png",
  alt: "Website Preview"
});
</script>

<style scoped>
.hero-section {
  background: linear-gradient(135deg, #f8f9ff 0%, #e8f2ff 100%);
  position: relative;
  overflow: hidden;
  border-bottom-left-radius: 94% 14%;
  border-bottom-right-radius: 94% 14%;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: radial-gradient(circle, rgba(0, 123, 255, 0.1) 1px, transparent 1px);
  background-size: 20px 20px;
  opacity: 0.3;
  border-bottom-left-radius: 94% 14%;
  border-bottom-right-radius: 94% 14%;
}

.hero-title {
  font-size: 3.5rem;
  max-width: 600px;
  color: #003589;
  letter-spacing: -0.02em;
}

.website-preview-image {
  height: 500px;
  object-fit: cover;
}

.hex-card {
  bottom: -100px;
  left: -10px;
  z-index: 10;
  min-width: 250px;
}

.congratulations-card {
  bottom: -35px;
  right: 31px;
  z-index: 10;
  max-width: 280px;
}

.congratulations-title {
  font-size: 1.5rem;
  line-height: 1.2;
}

.congratulations-text {
  font-size: 1rem;
  line-height: 1.2;
}

.cursor-pointer {
  cursor: pointer;
}

.color-swatch:hover {
  transform: scale(1.05);
  transition: transform 0.2s ease;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hex-card {
    bottom: -5px;
    left: -5px;
    padding: 0.5rem;
    min-width: 100px;
  }
  
  .congratulations-card {
    bottom: -5px;
    right: -5px;
    padding: 0.5rem;
    max-width: 140px;
  }
  
  .congratulations-title {
    font-size: 0.9rem;
  }
  
  .congratulations-text {
    font-size: 0.8rem;
  }
}
</style>

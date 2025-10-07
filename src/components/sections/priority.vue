<template>
  <section class="priority-section py-5">
    <div class="container">
      <h2 class="section-title text-center">Make Your Success a Priority</h2>
      <div class="row align-items-center">
        <!-- Left Content - Image -->
        <div class="col-lg-6 mb-4 mb-lg-0">
          <div class="image-wrapper position-relative">
            <img
              src="/public/quran.png"
              alt="Quran"
              class="quran-image img-fluid"
            />
            <img
              src="/public/quran effect.png"
              alt="Quran Effect"
              class="quran-effect img-fluid"
            />
          </div>
        </div>

        <!-- Right Content - Text -->
        <div class="col-lg-6">
          <div class="features-list">
            <div class="feature-item d-flex mb-4">
              <div class="feature-number me-4">01</div>
              <div class="feature-content">
                <h3 class="feature-title mb-2">Learn Arabic</h3>
                <p class="feature-text">
                  If you've been researching exactly what skill you want to
                  learn, or if you just need one more skill to round out your
                  resume .
                </p>
              </div>
            </div>

            <div class="feature-item d-flex mb-4">
              <div class="feature-number me-4">02</div>
              <div class="feature-content">
                <h3 class="feature-title mb-2">Learn Tajweed</h3>
                <p class="feature-text">
                  If you've been researching exactly what skill you want to
                  learn, or if you just need one more skill to round out your
                  resume .
                </p>
              </div>
            </div>

            <div class="feature-item d-flex mb-4">
              <div class="feature-number me-4">03</div>
              <div class="feature-content">
                <h3 class="feature-title mb-2">Quran For Kids</h3>
                <p class="feature-text">
                  If you've been researching exactly what skill you want to
                  learn, or if you just need one more skill to round out your
                  resume .
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.priority-section {
  background: white;
}

.image-wrapper {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.quran-image {
  position: absolute;
  top: -120px;
  left: 0;
  max-width: 100%;
  height: auto;
}

.quran-effect {
  max-width: 100%;
  height: auto;
  margin-top: -50px;
}

.section-title {
  margin-bottom: 10rem;
  font-size: 2.5rem;
  font-weight: 700;
  color: #0a1f44;
  line-height: 1.3;
}

.feature-item {
  align-items: flex-start;
}

.feature-number {
  font-size: 3rem;
  font-weight: 700;
  color: #00bfa5;
  min-width: 80px;
  background: white;
  border: 1px solid #f0f0f0;
  border-radius: 50%;
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.feature-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0a1f44;
}

.feature-text {
  color: #666;
  font-size: 1rem;
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 991px) {
  .section-title {
    font-size: 2rem;
    text-align: center;
  }

  .features-list {
    margin-top: 2rem;
  }
}

@media (max-width: 767px) {
  .section-title {
    font-size: 1.75rem;
  }

  .feature-number {
    font-size: 2rem;
    width: 60px;
    height: 60px;
    min-width: 60px;
  }

  .feature-title {
    font-size: 1.25rem;
  }

  .feature-text {
    font-size: 0.9rem;
  }
}
</style>

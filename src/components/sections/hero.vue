<template>
  <section class="hero-section">
    <div class="mx-5">
      <div class="hero-card">
        <div class="row align-items-center">
          <!-- Left Content -->
          <div class="col-lg-6 mb-5 mb-lg-0">
            <div class="hero-content">
              <p class="arabic-text mb-3">
                بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ
              </p>
              <h1 class="hero-title mb-4">
                We are online<br />
                <span class="text-primary">Quran</span> teacher<br />
                for evreyone
              </h1>
              <button class="btn btn-success btn-lg px-4 py-2">
                Start Learning Now
              </button>
            </div>
          </div>

          <!-- Right Content -->
          <div class="col-lg-6">
            <div
              class="hero-image-wrapper position-relative d-flex justify-content-lg-end"
            >
              <div class="masked-container">
                <div class="masked"></div>
                <div class="masked-border"></div>

                <!-- Stats Cards -->
                <div class="stat-card stat-card-1">
                  <div class="stat-number">65k+</div>
                  <div class="stat-label">Enrolled Students</div>
                </div>

                <div class="stat-card stat-card-2">
                  <div class="stat-number">25+</div>
                  <div class="stat-label">Online Teachers</div>
                </div>
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
.hero-section {
  background: white;
  position: relative;
}

.hero-card {
  background: linear-gradient(135deg, #e8f4f8 0%, #f0e8f8 100%);
  border-radius: 30px;
  padding: 40px;
  overflow: hidden;
  position: relative;
}

.arabic-text {
  color: #ffc280;
  font-size: 1.2rem;
  font-weight: 500;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  color: #0a1f44;
  line-height: 1.2;
}

.text-primary {
  color: #e91e63 !important;
}

.btn-success {
  background-color: #00bfa5;
  border-color: #00bfa5;
  border-radius: 8px;
  font-weight: 600;
}

.btn-success:hover {
  background-color: #00a690;
  border-color: #00a690;
}

.hero-image-wrapper {
  position: relative;
}

.image-container {
  position: relative;
  background: white;
  z-index: 2;
  max-width: 450px;
  margin: 0 auto;
}

.arch-image {
  display: block;
  width: 100%;
  height: auto;
}

.stat-card {
  position: absolute;
  background: white;
  border-radius: 12px;
  padding: 20px 30px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  z-index: 3;
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  transition: all 0.3s ease;
}

.stat-card-1 {
  top: 15%;
  left: -15%;
  transform: translateX(0);
}

.stat-card-2 {
  bottom: 10%;
  left: -8%;
  transform: translateX(0);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 5px;
  text-align: center;
}

.stat-card-1 .stat-number {
  color: #00bfa5;
}

.stat-card-2 .stat-number {
  color: #e91e63;
}

.stat-label {
  font-size: 0.9rem;
  color: #666;
  text-align: center;
}

@media (max-width: 1200px) {
  .stat-card {
    width: 200px;
    height: 200px;
    padding: 18px 25px;
  }

  .stat-card-1 {
    top: 12%;
    left: -12%;
  }

  .stat-card-2 {
    bottom: 8%;
    left: -6%;
  }
}

@media (max-width: 991px) {
  .hero-title {
    font-size: 2.5rem;
  }

  .stat-card {
    width: 150px;
    height: 130px;
    padding: 15px 20px;
  }

  .stat-number {
    font-size: 2rem;
  }

  /* Center content on medium screens */
  .hero-content {
    text-align: center;
  }

  .hero-image-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  /* Adjust stat cards positioning for centered layout */
  .stat-card-1 {
    top: 8%;
    left: -20%;
    transform: translateX(0);
  }

  .stat-card-2 {
    bottom: 15%;
    left: -15%;
    transform: translateX(0);
  }
}

@media (max-width: 767px) {
  .hero-card {
    border-radius: 20px;
    padding: 20px;
  }

  .hero-title {
    font-size: 2rem;
  }

  .stat-card {
    width: 140px;
    height: 120px;
    padding: 12px 16px;
    font-size: 0.8rem;
  }

  .stat-card-1 {
    top: 5%;
    left: -25%;
    right: auto;
  }

  .stat-card-2 {
    bottom: 10%;
    left: -20%;
    right: auto;
  }

  .stat-number {
    font-size: 1.5rem;
  }
}

@media (max-width: 575px) {
  .stat-card {
    width: 120px;
    height: 100px;
    padding: 10px 14px;
  }

  .stat-card-1 {
    top: 8%;
    left: -13%;
  }

  .stat-card-2 {
    bottom: 26%;
    left: -14%;
  }

  .stat-number {
    font-size: 1.3rem;
  }

  .stat-label {
    font-size: 0.75rem;
  }
}

@media (max-width: 400px) {
  .stat-card {
    width: 100px;
    height: 85px;
    padding: 8px 12px;
  }

  .stat-card-1 {
    top: 5%;
    left: -35%;
  }

  .stat-card-2 {
    bottom: 8%;
    left: -30%;
  }

  .stat-number {
    font-size: 1.1rem;
  }

  .stat-label {
    font-size: 0.7rem;
  }
}
.arch-card {
  max-width: 380px; /* عدّل المقاس حسب الحاجة */
  margin: 20px auto;
}
.arch-svg {
  width: 100%;
  height: auto;
  display: block;
}

.arch-card,
.arch-svg {
  background: transparent;
}
.masked-container {
  position: relative;
  width: 100%;
  max-width: 450px;
  height: 750px;
}

.masked {
  width: 100%;
  height: 100%;
  background: url("/public/quranMan.jpg") center no-repeat;
  background-size: cover;
  -webkit-mask-image: url("/public/mask.png");
  mask-image: url("/public/mask.png");
  -webkit-mask-size: contain;
  mask-size: contain;

  -webkit-mask-repeat: no-repeat;
  mask-repeat: no-repeat;
  -webkit-mask-position: center;
  mask-position: center;

  /* اختياري لو الماسك معمول ألفا مش لومننس */
  mask-mode: alpha;
  position: relative;
  z-index: 2;
}

.masked-border {
  width: 100%;
  height: 107%;
  position: absolute;
  top: -22px;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url("/public/bordermask.png");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  z-index: 1;
  pointer-events: none;
}

/* Responsive adjustments for the mask */
@media (max-width: 1200px) {
  .masked-container {
    height: 650px;
    max-width: 400px;
  }
}

@media (max-width: 991px) {
  .masked-container {
    height: 600px;
    max-width: 350px;
  }

  .masked {
    -webkit-mask-size: contain;
    mask-size: contain;
    -webkit-mask-position: center;
    mask-position: center;
  }

  .masked-border {
    background-size: contain;
    background-position: center;
  }
}

@media (max-width: 767px) {
  .masked-container {
    height: 500px;
    max-width: 300px;
  }

  .hero-image-wrapper {
    padding: 20px;
    display: flex;
    justify-content: center;
  }

  .masked {
    -webkit-mask-size: contain;
    mask-size: contain;
    -webkit-mask-position: center;
    mask-position: center;
  }

  .masked-border {
    background-size: contain;
    background-position: center;
  }
}

@media (max-width: 575px) {
  .masked-container {
    height: 400px;
    max-width: 250px;
  }

  .masked {
    -webkit-mask-size: contain;
    mask-size: contain;
    -webkit-mask-position: center;
    mask-position: center;
  }

  .masked-border {
    background-size: contain;
    background-position: center;
  }
}

@media (max-width: 400px) {
  .masked-container {
    height: 350px;
    max-width: 200px;
  }
}
</style>

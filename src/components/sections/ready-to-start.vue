<template>
  <section class="ready-section">
    <div class="container">
      <div class="ready-banner">
        <!-- Background Image -->
        <div class="background-image"></div>

        <!-- Lantern Image -->
        <div class="lantern-image">
          <img src="/read-pphanos.png" alt="Lantern" />
        </div>

        <!-- Content -->
        <div
          class="row align-items-center justify-content-center h-100 mx-auto"
        >
          <div class="col-lg-8">
            <div class="ready-content">
              <h2 class="ready-title">Ready to start?</h2>
              <p class="ready-subtitle">
                The best players don't always make the best coaches.
              </p>
            </div>
          </div>
          <div class="col-lg-4 text-lg-end">
            <button class="btn btn-get-started">Get Started</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.ready-section {
  padding: 60px 0;
  background: white;
}

.ready-banner {
  background: linear-gradient(135deg, #34b3a0 0%, #2a9d8f 100%);
  border-radius: 30px;
  padding: 60px 40px;
  position: relative;
  overflow: hidden;
  min-height: 200px;
  display: flex;
  align-items: center;
}

/* Background Image */
.background-image {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url("/ready.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0.3;
  z-index: 1;
}

/* Lantern Image */
.lantern-image {
  position: absolute;
  top: 20px;
  left: 20px;
  z-index: 2;
  animation: float 3s ease-in-out infinite;
  animation-delay: 0.8s;
}

.lantern-image img {
  width: 160px;
  height: auto;
  display: block;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
}

/* Content */
.ready-content {
  position: relative;
  z-index: 3;
}

.ready-title {
  font-size: 3rem;
  font-weight: 700;
  color: white;
  margin-bottom: 15px;
  line-height: 1.2;
}

.ready-subtitle {
  font-size: 1.2rem;
  color: white;
  margin-bottom: 0;
  opacity: 0.9;
}

.btn-get-started {
  background: white;
  color: #2a9d8f;
  border: none;
  padding: 15px 30px;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1.1rem;
  transition: all 0.3s ease;
  position: relative;
  z-index: 3;
}

.btn-get-started:hover {
  background: #f8f9fa;
  color: #2a9d8f;
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

/* Responsive Design */
@media (max-width: 991px) {
  .ready-banner {
    padding: 40px 30px;
    text-align: center;
  }

  .ready-title {
    font-size: 2.5rem;
  }

  .ready-subtitle {
    font-size: 1.1rem;
  }

  .lantern-image {
    display: none;
  }
}

@media (max-width: 767px) {
  .ready-banner {
    padding: 30px 20px;
    border-radius: 20px;
  }

  .ready-title {
    font-size: 2rem;
  }

  .ready-subtitle {
    font-size: 1rem;
  }

  .btn-get-started {
    padding: 12px 25px;
    font-size: 1rem;
  }
}

@media (max-width: 575px) {
  .ready-section {
    padding: 40px 0;
  }

  .ready-banner {
    padding: 25px 15px;
  }

  .ready-title {
    font-size: 1.8rem;
  }
}
</style>

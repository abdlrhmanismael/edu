<template>
  <section class="hero-section bg-light-subtle">
    <div class="container-fluid ms-lg-5">
      <div class="row align-items-center">
        <!-- Left copy -->
        <div class="col-lg-6">
          <div class="d-flex align-items-center gap-2 text-primary mb-3">
            <span
              class="d-inline-flex align-items-center justify-content-center emoji"
              >⚡</span
            >
            <span class="fw-medium">Learn From 20,000+ Quality Courses</span>
          </div>

          <h1 class="display-4 fw-bold lh-1 text-dark mb-3">
            <span class="highlight bg-warning px-3 py-1 d-inline-block mb-2"
              >Discover</span
            >
            the
            <br />
            <span>Unlimited Skilful</span>
            <br />
            <span class="text-primary">Quality Courses</span>
          </h1>

          <a href="#" class="btn btn-primary btn-lg px-4">Start Learning Now</a>
          <p class="mt-3 fw-bold">
            <span class="text-primary"> No credit card required.</span>
            By clicking ‘Start a Free Trial’
          </p>
        </div>

        <!-- Right visuals -->
        <div class="col-lg-6">
          <div
            class="hero-visuals d-flex justify-content-between align-items-center"
          >
            <!-- Left column with rectangle and circle images -->
            <div
              class="left-images d-flex flex-column gap-3 gap-lg-4 align-items-center"
            >
              <div class="img-rect rounded-4 overflow-hidden shadow-sm">
                <img
                  src="/assets/img/theme-four/hero_one.jpg"
                  alt="workspace"
                  class="img-fill"
                />
              </div>
              <div class="img-large rounded-circle overflow-hidden shadow-sm">
                <img
                  src="/assets/img/theme-four/hero_two.jpg"
                  alt="student"
                  class="img-fill"
                />
              </div>
            </div>
            <!-- Right column with third image -->
            <div class="right-image ms-3 ms-lg-4">
              <div class="image_thumb overflow-hidden shadow-sm">
                <img
                  src="/assets/img/theme-four/hero_three.jpg"
                  alt="learning"
                  class="img-fill"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.hero-section {
  background-color: #f6f7fc;
}
.py-lg-7 {
  padding-top: 5rem;
  padding-bottom: 5rem;
}
.emoji {
  width: 28px;
  height: 28px;
  font-size: 18px;
}
.highlight {
  border-radius: 0.25rem;
}
.hero-visuals {
  width: 100%;
  //   max-width: 520px;
  margin: 0 auto;
}

.img-fill {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.img-large {
  width: 100%;
  max-width: 200px;
  height: 200px;
}

.img-rect {
  width: 100%;
  max-width: 380px;
  height: 223px;
  border-radius: 6rem !important;
}

.img-circle-small {
  width: 120px;
  height: 120px;
}

.image_thumb {
  border-bottom-left-radius: 12rem;
  border-bottom-right-radius: 12rem;
  overflow: hidden;
}

@media (max-width: 991.98px) {
  .hero-visuals {
    max-width: 100%;
    padding: 0 1rem;
    gap: 1rem !important;
    flex-direction: column;
    align-items: center;
  }

  .img-large {
    max-width: 120px;
    height: 120px;
  }

  .img-rect {
    max-width: 200px;
    height: 120px;
  }

  .image_thumb {
    margin-top: 1rem;
  }
}

@media (max-width: 768px) {
  .hero-visuals {
    padding: 0 0.5rem;
    gap: 0.5rem !important;
  }

  .img-large {
    max-width: 100px;
    height: 100px;
  }

  .img-rect {
    max-width: 180px;
    height: 100px;
  }
}

@media (max-width: 576px) {
  .hero-visuals {
    padding: 0 0.25rem;
  }

  .img-large {
    max-width: 80px;
    height: 80px;
  }

  .img-rect {
    max-width: 150px;
    height: 80px;
  }

  .image_thumb {
    margin-top: 0.5rem;
  }
}
</style>

<template>
  <section class="teachers-section py-5">
    <div class="container">
      <div class="row align-items-center">
        <!-- Left Side - Images -->
        <div class="col-lg-6 mb-4 mb-lg-0">
          <div
            class="position-relative d-flex justify-content-center align-items-center gap-3"
          >
            <div class="border-image rounded">
              <img
                src="/public/person.png"
                alt=""
                class="rounded-5 big-image"
              />
            </div>
            <div class="d-flex flex-column gap-3">
              <div>
                <img src="/public/person.png" alt="" />
              </div>
              <div>
                <img src="/public/person.png" alt="" />
              </div>
            </div>

            <!-- Center Badge -->
            <div class="center-badge">
              <div class="badge-circle">
                <div class="badge-icon">
                  <img
                    src="/public/quran icon.png"
                    alt="Quran Icon"
                    class="quran-icon"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Side - Content -->
        <div class="col-lg-6">
          <div class="content-wrapper">
            <h2 class="section-heading">
              Expert Quran Teachers Available for Private Lessons Anytime
            </h2>
            <p class="section-description">
              If you've been researching exactly what skill you want to learn,
              or if you just need one more skill to round out your resume.
              Whether fully virtual, fully in-person or something in between,
              explore.
            </p>

            <ul class="features-list">
              <li class="feature-item">
                <span class="icon-wrapper">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    height="20"
                    fill="currentColor"
                    viewBox="0 0 16 16"
                  >
                    <path
                      d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"
                    />
                    <path
                      d="M10.97 4.97a.235.235 0 0 0-.02.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-1.071-1.05z"
                    />
                  </svg>
                </span>
                <span class="feature-text"
                  >Get access to 4,000+ of our top courses</span
                >
              </li>
              <li class="feature-item">
                <span class="icon-wrapper">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    height="20"
                    fill="currentColor"
                    viewBox="0 0 16 16"
                  >
                    <path
                      d="M8 4.754a3.246 3.246 0 1 0 0 6.492 3.246 3.246 0 0 0 0-6.492zM5.754 8a2.246 2.246 0 1 1 4.492 0 2.246 2.246 0 0 1-4.492 0z"
                    />
                    <path
                      d="M9.796 1.343c-.527-1.79-3.065-1.79-3.592 0l-.094.319a.873.873 0 0 1-1.255.52l-.292-.16c-1.64-.892-3.433.902-2.54 2.541l.159.292a.873.873 0 0 1-.52 1.255l-.319.094c-1.79.527-1.79 3.065 0 3.592l.319.094a.873.873 0 0 1 .52 1.255l-.16.292c-.892 1.64.901 3.434 2.541 2.54l.292-.159a.873.873 0 0 1 1.255.52l.094.319c.527 1.79 3.065 1.79 3.592 0l.094-.319a.873.873 0 0 1 1.255-.52l.292.16c1.64.893 3.434-.902 2.54-2.541l-.159-.292a.873.873 0 0 1 .52-1.255l.319-.094c1.79-.527 1.79-3.065 0-3.592l-.319-.094a.873.873 0 0 1-.52-1.255l.16-.292c.893-1.64-.902-3.433-2.541-2.54l-.292.159a.873.873 0 0 1-1.255-.52l-.094-.319z"
                    />
                  </svg>
                </span>
                <span class="feature-text">Popular topics to learn now</span>
              </li>
              <li class="feature-item">
                <span class="icon-wrapper">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    height="20"
                    fill="currentColor"
                    viewBox="0 0 16 16"
                  >
                    <path
                      d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10z"
                    />
                  </svg>
                </span>
                <span class="feature-text"
                  >Find the right instructor for you</span
                >
              </li>
            </ul>

            <button class="btn btn-primary btn-get-started">Get Started</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.teachers-section {
  background: white;
  padding: 60px 0;
}

.border-image {
  flex-shrink: 0;
}

.border-image img {
  width: 280px;
  height: 400px;
  object-fit: cover;
  border-radius: 20px;
}

.d-flex.flex-column img {
  width: 180px;
  height: 190px;
  object-fit: cover;
  border-radius: 15px;
}
.big-image {
  width: 286px !important;
  height: 332px !important;
}

.center-badge {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
}

.badge-circle {
  width: 200px;
  height: 200px;
  background: #00bfa5;
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
  box-shadow: 0 8px 20px rgba(0, 191, 165, 0.3);
}

.badge-icon {
  width: 50px;
  height: 50px;
  background: white;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 8px 0;
}

.quran-icon {
  width: 35px;
  height: 35px;
  object-fit: contain;
}

.content-wrapper {
  padding: 0 20px;
}

.section-heading {
  font-size: 2.5rem;
  font-weight: 700;
  color: #0a1f44;
  margin-bottom: 20px;
  line-height: 1.2;
}

.section-description {
  color: #666;
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 30px;
}

.features-list {
  list-style: none;
  padding: 0;
  margin: 0 0 30px 0;
}

.feature-item {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
  color: #0a1f44;
  font-size: 1rem;
  font-weight: 500;
}

.icon-wrapper {
  width: 30px;
  height: 30px;
  background: #e8f9f6;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 12px;
  flex-shrink: 0;
  color: #00bfa5;
}

.feature-text {
  flex: 1;
}

.btn-get-started {
  background-color: #00bfa5;
  border-color: #00bfa5;
  color: white;
  padding: 12px 32px;
  font-size: 1rem;
  font-weight: 600;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.btn-get-started:hover {
  background-color: #00a690;
  border-color: #00a690;
}

@media (max-width: 991px) {
  .section-heading {
    font-size: 2rem;
  }

  .content-wrapper {
    padding: 0;
    margin-top: 30px;
  }

  .border-image img {
    width: 240px;
    height: 350px;
  }

  .d-flex.flex-column img {
    width: 150px;
    height: 165px;
  }
}

@media (max-width: 767px) {
  .section-heading {
    font-size: 1.75rem;
  }

  .border-image img {
    width: 200px;
    height: 300px;
  }

  .d-flex.flex-column img {
    width: 120px;
    height: 140px;
  }

  .badge-circle {
    width: 180px;
    height: 180px;
    padding: 15px;
  }

  .badge-icon {
    width: 40px;
    height: 40px;
  }

  .quran-icon {
    width: 28px;
    height: 28px;
  }
}

@media (max-width: 576px) {
  .border-image img {
    width: 160px;
    height: 250px;
  }

  .d-flex.flex-column img {
    width: 100px;
    height: 118px;
  }

  .section-heading {
    font-size: 1.5rem;
  }

  .badge-circle {
    width: 120px;
    height: 120px;
    padding: 12px;
  }

  .badge-icon {
    width: 35px;
    height: 35px;
  }

  .quran-icon {
    width: 24px;
    height: 24px;
  }

  .center-badge {
    top: 50%;
    left: 70%;
  }
}
</style>

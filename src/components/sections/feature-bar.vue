<template>
  <section class="feature-bar-section">
    <div class="container">
      <div class="feature-bar">
        <div class="row g-0">
          <div
            v-for="(feature, index) in features"
            :key="index"
            class="col-md-4"
          >
            <div class="feature-card d-flex align-items-center">
              <div class="feature-icon me-3 ms-3 ms-md-0">
                <i :class="feature.icon"></i>
              </div>
              <div class="feature-text">
                <span class="text-white">{{ feature.text }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Feature {
  icon: string;
  text: string;
}

const features: Feature[] = [
  {
    icon: "fas fa-lightbulb",
    text: "Get the desired certificate delivered",
  },
  {
    icon: "fas fa-book-open",
    text: "Help you understand yourself better",
  },
  {
    icon: "fas fa-bell",
    text: "Give the right advice to help life career",
  },
];
</script>

<style lang="scss" scoped>
.feature-bar-section {
  padding: 2rem;
  overflow: hidden;
}

.feature-bar {
  background: linear-gradient(135deg, #007bff 0%, #0056b3 100%);
  border-radius: 7rem;
  padding: 2rem 2rem;
  box-shadow: 0 4px 20px rgba(0, 123, 255, 0.3);
}

.feature-card {
  padding: 1.5rem 2rem;
  height: 100%;
  display: flex;
  align-items: center;
  border-right: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;

  &:last-child {
    border-right: none;
  }

  &:hover {
    transform: translateY(-2px);
  }
}

.feature-icon {
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.15);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8rem;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 4px 15px rgba(255, 255, 255, 0.1);
  position: relative;

  &::before {
    content: "";
    position: absolute;
    left: -30px;
    top: 50%;
    transform: translateY(-50%);
    width: 60px;
    height: 60px;
    background: #0056b3;
    border-radius: 50%;
    z-index: 1;
    clip-path: polygon(50% 0%, 50% 100%, 0% 100%, 0% 0%);
  }
}

.feature-text {
  font-size: 1rem;
  line-height: 1.4;
  font-weight: 500;
}

// Tablet styles
@media (max-width: 992px) {
  .feature-bar {
    padding: 1.5rem 1.5rem;
  }

  .feature-card {
    padding: 1.2rem 1.5rem;
  }

  .feature-icon {
    width: 55px;
    height: 55px;
    font-size: 1.6rem;

    &::before {
      left: -27.5px;
      width: 55px;
      height: 55px;
    }
  }

  .feature-text {
    font-size: 0.95rem;
  }
}

// Mobile styles
@media (max-width: 768px) {
  .feature-bar-section {
    padding: 1rem;
  }

  .feature-bar {
    padding: 1.5rem 1rem;
    border-radius: 4rem;
  }

  .feature-card {
    padding: 1rem 1.2rem;
    border-right: none;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    flex-direction: row;
    text-align: left;
    gap: 1rem;

    &:last-child {
      border-bottom: none;
    }
  }

  .feature-icon {
    width: 50px;
    height: 50px;
    font-size: 1.5rem;
    flex-shrink: 0;

    &::before {
      left: -25px;
      width: 50px;
      height: 50px;
    }
  }

  .feature-text {
    font-size: 0.9rem;
    line-height: 1.3;
  }
}

// Small mobile styles
@media (max-width: 576px) {
  .feature-bar-section {
    padding: 0.5rem;
  }

  .feature-bar {
    padding: 1rem 0.75rem;
    border-radius: 3rem;
  }

  .feature-card {
    padding: 0.75rem 0.5rem;
    gap: 0.75rem;
    flex-direction: row;
    text-align: left;
  }

  .feature-icon {
    width: 45px;
    height: 45px;
    font-size: 1.3rem;

    &::before {
      left: -22.5px;
      width: 45px;
      height: 45px;
    }
  }

  .feature-text {
    font-size: 0.85rem;
    line-height: 1.2;
  }
}

// Extra small screens
@media (max-width: 400px) {
  .feature-bar {
    padding: 0.75rem 0.5rem;
    border-radius: 2.5rem;
  }

  .feature-card {
    padding: 0.5rem 0.25rem;
    flex-direction: row;
    text-align: left;
    gap: 0.5rem;
  }

  .feature-icon {
    width: 40px;
    height: 40px;
    font-size: 1.1rem;

    &::before {
      left: -20px;
      width: 40px;
      height: 40px;
    }
  }

  .feature-text {
    font-size: 0.8rem;
  }
}
</style>

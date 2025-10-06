<template>
  <section class="testimonials-section">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <div class="testimonials-wrapper">
            <!-- Background Shapes -->
            <div class="bg-shapes">
              <div class="shape-blue-main"></div>
              <div class="shape-yellow-main"></div>
            </div>

            <!-- Main Content Container -->
            <div class="testimonials-main-content">
              <!-- Left Side - Image -->
              <div class="testimonial-image-container">
                <div class="image-wrapper">
                  <img
                    :src="currentTestimonial.image"
                    :alt="currentTestimonial.name"
                  />
                </div>
              </div>

              <!-- Right Side - Content Card -->
              <div class="testimonial-content-card">
                <!-- Header -->
                <div class="testimonials-header">
                  <h2 class="section-title">
                    Student <span class="text-primary">Testimonials</span>
                  </h2>
                  <div class="title-underline"></div>
                  <div class="dots-pattern">
                    <div class="dots"></div>
                  </div>
                </div>

                <!-- Swiper Container -->
                <div class="testimonials-swiper-container">
                  <swiper
                    :modules="modules"
                    :slides-per-view="1"
                    :space-between="0"
                    :pagination="{ clickable: true }"
                    :autoplay="{ delay: 5000 }"
                    class="testimonials-swiper"
                    @swiper="onSwiper"
                    @slide-change="onSlideChange"
                  >
                    <swiper-slide
                      v-for="(testimonial, index) in testimonials"
                      :key="index"
                    >
                      <div class="testimonial-content">
                        <div class="quote-icon">
                          <svg
                            width="40"
                            height="30"
                            viewBox="0 0 40 30"
                            fill="none"
                          >
                            <path
                              d="M8.33333 30C6.03333 30 4.08333 29.1667 2.48333 27.5C0.883333 25.8333 0.0833333 23.8333 0.0833333 21.5C0.0833333 19.1667 0.883333 17.1667 2.48333 15.5C4.08333 13.8333 6.03333 13 8.33333 13C8.83333 13 9.33333 13.0833 9.83333 13.25C10.3333 13.4167 10.8333 13.6667 11.3333 14C11.3333 11.6667 10.5333 9.66667 8.93333 8C7.33333 6.33333 5.38333 5.5 3.08333 5.5V0.5C7.08333 0.5 10.4167 1.91667 13.0833 4.75C15.75 7.58333 17.0833 11.1667 17.0833 15.5C17.0833 19.8333 15.75 23.4167 13.0833 26.25C10.4167 29.0833 7.08333 30.5 3.08333 30.5H8.33333V30ZM31.25 30C28.95 30 27 29.1667 25.4 27.5C23.8 25.8333 23 23.8333 23 21.5C23 19.1667 23.8 17.1667 25.4 15.5C27 13.8333 28.95 13 31.25 13C31.75 13 32.25 13.0833 32.75 13.25C33.25 13.4167 33.75 13.6667 34.25 14C34.25 11.6667 33.45 9.66667 31.85 8C30.25 6.33333 28.3 5.5 26 5.5V0.5C30 0.5 33.3333 1.91667 36 4.75C38.6667 7.58333 40 11.1667 40 15.5C40 19.8333 38.6667 23.4167 36 26.25C33.3333 29.0833 30 30.5 26 30.5H31.25V30Z"
                              fill="#007BFF"
                            />
                          </svg>
                        </div>
                        <p class="testimonial-text">{{ testimonial.text }}</p>
                        <div class="testimonial-author">
                          <h5 class="author-name">{{ testimonial.name }}</h5>
                        </div>
                      </div>
                    </swiper-slide>
                  </swiper>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Autoplay } from "swiper/modules";
import { ref, computed } from "vue";
import "swiper/css";
import "swiper/css/pagination";

export default {
  name: "TestimonialsSection",
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const modules = [Pagination, Autoplay];
    const currentSlideIndex = ref(0);

    const testimonials = [
      {
        name: "James Foster",
        title: "Student",
        text: "I truly believe in lifelong learning, and these platforms are a fantastic place to gain new knowledge directly from industry-leading professionals.",
        image: "/person.png",
      },
      {
        name: "Sarah Johnson",
        title: "Graduate Student",
        text: "The courses here have transformed my career. The instructors are knowledgeable and the content is always up-to-date with industry standards.",
        image: "/person.png",
      },
      {
        name: "Michael Chen",
        title: "Professional Developer",
        text: "Amazing learning experience! The practical approach and real-world projects helped me advance my skills significantly.",
        image: "/person.png",
      },
    ];

    const currentTestimonial = computed(() => {
      return testimonials[currentSlideIndex.value];
    });

    const onSwiper = (swiper) => {
      // Store swiper instance if needed
    };

    const onSlideChange = (swiper) => {
      currentSlideIndex.value = swiper.activeIndex;
    };

    return {
      modules,
      testimonials,
      currentTestimonial,
      onSwiper,
      onSlideChange,
    };
  },
};
</script>

<style lang="scss" scoped>
.testimonials-section {
  padding: 100px 0;
  background: #f8f9fa;
  position: relative;
  overflow: hidden;
}

.testimonials-wrapper {
  position: relative;
  z-index: 2;
}

.bg-shapes {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;

  .shape-blue-main {
    position: absolute;
    top: 20%;
    left: -2%;
    width: 280px;
    height: 350px;
    background: linear-gradient(135deg, #007bff 0%, #0056cc 100%);
    border-radius: 20px;
    transform: rotate(-10deg);
    z-index: 1; /* Under the left image */
  }

  .shape-yellow-main {
    position: absolute;
    top: 10%;
    left: 12%;
    width: 220px;
    height: 280px;
    background: linear-gradient(135deg, #ffd700 0%, #ffa500 100%);
    border-radius: 15px;
    transform: rotate(20deg);
    z-index: 1; /* Under the left image */
  }
}

.testimonials-main-content {
  display: flex;
  align-items: center;
  gap: 60px;
  position: relative;
  z-index: 10;
  max-width: 1200px;
  margin: 0 auto;

  @media (max-width: 992px) {
    flex-direction: column;
    gap: 40px;
  }
}

.testimonial-image-container {
  flex-shrink: 0;
  position: relative;
  z-index: 5; /* Above the background shapes underneath */

  .image-wrapper {
    position: relative;

    img {
      width: 280px;
      height: 350px;
      border-radius: 20px;
      object-fit: cover;
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);

      @media (max-width: 992px) {
        width: 250px;
        height: 300px;
      }

      @media (max-width: 576px) {
        width: 200px;
        height: 250px;
      }
    }
  }
}

.testimonial-content-card {
  flex: 1;
  background: white;
  border-radius: 25px;
  padding: 50px 40px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
  position: relative;
  max-width: 600px;
  z-index: 10; /* Below the blue accent shape on top */

  @media (max-width: 768px) {
    padding: 40px 30px;
    margin: 0 20px;
  }

  @media (max-width: 576px) {
    padding: 30px 20px;
    margin: 0 10px;
  }
}

.testimonials-header {
  margin-bottom: 40px;
  position: relative;

  .section-title {
    font-size: 2.2rem;
    font-weight: 700;
    color: #2c3e50;
    margin-bottom: 15px;
    line-height: 1.2;

    .text-primary {
      color: #007bff;
    }

    @media (max-width: 768px) {
      font-size: 1.8rem;
    }
  }

  .title-underline {
    width: 60px;
    height: 4px;
    background: linear-gradient(90deg, #ffd700 0%, #ffa500 100%);
    border-radius: 2px;
    margin-bottom: 20px;
  }

  .dots-pattern {
    position: absolute;
    top: -10px;
    right: 0;

    .dots {
      width: 80px;
      height: 30px;
      background-image: radial-gradient(circle, #007bff 2px, transparent 2px);
      background-size: 8px 8px;
      opacity: 0.4;
    }
  }
}

.testimonials-swiper-container {
  .testimonials-swiper {
    padding-bottom: 50px;
  }
}

.testimonial-content {
  .quote-icon {
    margin-bottom: 25px;

    svg {
      width: 35px;
      height: 26px;
    }
  }

  .testimonial-text {
    font-size: 1.1rem;
    line-height: 1.7;
    color: #555;
    margin-bottom: 30px;
    font-style: italic;
    font-weight: 400;

    @media (max-width: 768px) {
      font-size: 1rem;
    }
  }

  .testimonial-author {
    .author-name {
      font-size: 1.2rem;
      font-weight: 600;
      color: #2c3e50;
      margin-bottom: 0;

      @media (max-width: 768px) {
        font-size: 1.1rem;
      }
    }
  }
}

// Swiper Pagination Styles
:deep(.swiper-pagination) {
  position: static;
  margin-top: 20px;
  text-align: left;

  .swiper-pagination-bullet {
    width: 12px;
    height: 12px;
    background: #ddd;
    opacity: 1;
    margin: 0 8px 0 0;
    transition: all 0.3s ease;

    &.swiper-pagination-bullet-active {
      background: #007bff;
      transform: scale(1.3);
    }
  }
}

// Responsive Design
@media (max-width: 1200px) {
  .bg-shapes {
    .shape-blue-main {
      width: 240px;
      height: 300px;
    }

    .shape-yellow-main {
      width: 180px;
      height: 240px;
    }
  }
}

@media (max-width: 992px) {
  .testimonials-section {
    padding: 80px 0;
  }

  .testimonials-main-content {
    text-align: center;
  }

  .bg-shapes {
    .shape-blue-main {
      top: 10%;
      left: -5%;
      width: 200px;
      height: 250px;
    }

    .shape-yellow-main {
      top: 5%;
      left: 8%;
      width: 150px;
      height: 200px;
    }
  }
}

@media (max-width: 768px) {
  .testimonials-section {
    padding: 60px 0;
  }

  .testimonials-main-content {
    gap: 30px;
  }

  .bg-shapes {
    .shape-blue-main {
      width: 160px;
      height: 200px;
      left: -8%;
    }

    .shape-yellow-main {
      width: 120px;
      height: 160px;
      left: 5%;
    }

    .shape-blue-accent {
      top: -2%;
      right: 5%;
      width: 60px;
      height: 30px;
    }
  }
}
</style>

<template>
  <section class="testmonial-section">
    <div class="container">
      <div class="testmonial-content border border-2">
        <div class="img-testmonial">
          <img
            src="/assets/img/theme-four/person.png"
            alt=""
            class="img-fill rounded rouned-5"
          />
        </div>
        <div class="polygon-one"></div>
        <div class="polygon-two"></div>
        <h1 class="title-testmonial">Student Testimonials</h1>

        <swiper
          :modules="modules"
          :slides-per-view="1"
          :space-between="0"
          :loop="true"
          :autoplay="{
            delay: 5000,
            disableOnInteraction: false,
          } as any"
          :pagination="{
            clickable: true,
            bulletClass: 'swiper-pagination-bullet testimonial-bullet',
            bulletActiveClass: 'swiper-pagination-bullet-active testimonial-bullet-active'
          } as any"
          class="testimonial-swiper"
        >
          <swiper-slide
            v-for="(testimonial, index) in testimonials"
            :key="index"
          >
            <div class="testimonial-slide">
              <div class="mb-3">
                <svg
                  width="48"
                  height="49"
                  viewBox="0 0 48 49"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M20.9062 16.1114V21.0332C20.9062 23.377 20.5468 25.627 19.828 27.7832C19.1405 29.9395 18.164 31.916 16.8984 33.7129C15.6327 35.5098 14.1405 37.0957 12.4218 38.4707C10.6718 39.8457 8.74992 40.9239 6.65617 41.7051C5.99992 41.9864 5.35149 41.9785 4.71086 41.6817C4.07024 41.3848 3.64055 40.8926 3.4218 40.2051C3.20305 39.5801 3.2343 38.9707 3.51555 38.377C3.7968 37.7832 4.24992 37.377 4.87492 37.1582C6.18742 36.627 7.4218 35.9551 8.57805 35.1426C9.7343 34.3301 10.7734 33.4004 11.6952 32.3535C12.6171 31.3067 13.4062 30.1426 14.0624 28.8614C14.7187 27.5801 15.2187 26.2364 15.5624 24.8301C14.6562 25.2989 13.6952 25.627 12.6796 25.8145C11.664 26.002 10.6093 26.002 9.51555 25.8145C7.2968 25.4707 5.41399 24.4707 3.86711 22.8145C2.32024 21.1582 1.43742 19.2207 1.21867 17.002C1.09367 15.5645 1.26555 14.1895 1.7343 12.877C2.20305 11.5645 2.89055 10.4239 3.7968 9.4551C4.70305 8.48635 5.78117 7.7051 7.03117 7.11135C8.28117 6.54885 9.62492 6.2676 11.0624 6.2676C12.4062 6.2676 13.6874 6.5176 14.9062 7.0176C16.0937 7.54885 17.1327 8.25979 18.0234 9.15042C18.914 10.041 19.6093 11.0801 20.1093 12.2676C20.6405 13.4864 20.9062 14.7676 20.9062 16.1114ZM46.7812 16.1114V21.0332C46.7812 23.377 46.4374 25.627 45.7499 27.7832C45.0312 29.9395 44.0468 31.916 42.7968 33.7129C41.5468 35.5098 40.0468 37.0957 38.2968 38.4707C36.5468 39.8457 34.6405 40.9239 32.578 41.7051C31.9218 41.9864 31.2734 41.9785 30.6327 41.6817C29.9921 41.3848 29.5468 40.8926 29.2968 40.2051C29.1093 39.5801 29.1562 38.9707 29.4374 38.377C29.7187 37.7832 30.1562 37.377 30.7499 37.1582C32.0937 36.627 33.3437 35.9551 34.4999 35.1426C35.6562 34.3301 36.6952 33.4004 37.6171 32.3535C38.539 31.3067 39.328 30.1426 39.9843 28.8614C40.6405 27.5801 41.1249 26.2364 41.4374 24.8301C40.5624 25.2989 39.6171 25.627 38.6015 25.8145C37.5859 26.002 36.5155 26.002 35.3905 25.8145C33.203 25.4707 31.328 24.4707 29.7655 22.8145C28.203 21.1582 27.328 19.2207 27.1405 17.002C27.0155 15.5645 27.1874 14.1895 27.6562 12.877C28.1249 11.5645 28.8046 10.4239 29.6952 9.4551C30.5859 8.48635 31.6562 7.7051 32.9062 7.11135C34.1562 6.54885 35.4999 6.2676 36.9374 6.2676C38.3124 6.2676 39.5937 6.5176 40.7812 7.0176C41.9687 7.54885 43.0077 8.25979 43.8984 9.15042C44.789 10.041 45.4999 11.0801 46.0312 12.2676C46.5312 13.4864 46.7812 14.7676 46.7812 16.1114Z"
                    fill="#0071DC"
                  />
                </svg>
              </div>
              <p class="w-75 fs-5">
                {{ testimonial.text }}
              </p>
              <p>{{ testimonial.name }}</p>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination, Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

const modules = [Navigation, Pagination, Autoplay];

const testimonials = [
  {
    name: "James Foster",
    text: "I truly believe in lifelong learning, and these platforms are a fantastic place to gain new knowledge directly from industry-leading experts.",
  },
  {
    name: "Sarah Johnson",
    text: "The quality of education here is outstanding. I've been able to advance my career significantly through the courses I've taken.",
  },
  {
    name: "Michael Chen",
    text: "The instructors are knowledgeable and the learning materials are comprehensive. This platform has transformed my professional skills.",
  },
  {
    name: "Emily Rodriguez",
    text: "I love the flexibility of learning at my own pace. The community support and resources available are exceptional.",
  },
  {
    name: "David Thompson",
    text: "The practical approach to learning with real-world projects has been invaluable for my career development.",
  },
];
</script>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
});
</script>

<style lang="scss" scoped>
.title-testmonial {
  margin-bottom: 2rem;
}
.testmonial-content {
  position: relative;
  padding: 7rem 0;
  padding-left: 10rem;
  margin-left: 20rem;
  background: #f2f3f8;
  background-image: url("/public/testmonials-bg.png");
  background-size: contain;
  background-position: right;
  background-repeat: no-repeat;
  border-radius: 2rem;
  .img-testmonial {
    position: absolute;
    left: -298px;
    top: 50%;
    transform: translateY(-50%);
    z-index: 1;
  }
}
.polygon-one {
  width: 250px;
  height: 578px;
  background: #0071dc;
  position: absolute;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  clip-path: polygon(17% 0, 100% 0, 76% 100%, 0 100%);
  position: absolute;
  left: -238px;
  z-index: 0;
}
.polygon-two {
  width: 250px;
  height: 516px;
  background: #ffc600;
  position: absolute;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  clip-path: polygon(17% 0, 100% 0, 76% 100%, 0 100%);
  position: absolute;
  left: -151px;
  z-index: 0;
}
// Swiper specific styles
.testimonial-swiper {
  .swiper-button-next,
  .swiper-button-prev {
    color: #0071dc;
    width: 40px;
    height: 40px;
    margin-top: -20px;

    &::after {
      font-size: 20px;
    }
  }

  .swiper-button-next {
    right: 20px;
  }

  .swiper-button-prev {
    left: 20px;
  }

  .swiper-pagination {
    position: relative;
    margin-top: 2rem;

    .testimonial-bullet {
      background: #ccc;
      opacity: 0.5;
      width: 12px;
      height: 12px;
      margin: 0 5px;
      border-radius: 50%;
      transition: all 0.3s ease;
    }

    .testimonial-bullet-active {
      background: #0071dc;
      opacity: 1;
    }
  }
}

.testimonial-slide {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  text-align: left;
}

// Mobile responsiveness - only for small screens
@media (max-width: 768px) {
  .testmonial-content {
    padding: 2rem 1.5rem;
    margin-left: 0;
    text-align: center;

    .img-testmonial {
      position: relative;
      left: auto;
      top: auto;
      transform: none;
      margin-bottom: 2rem;
      text-align: center;

      img {
        max-width: 200px;
        height: auto;
      }
    }

    .title-testmonial {
      font-size: 1.5rem;
      margin-bottom: 1.5rem;
    }

    p {
      width: 100% !important;
      font-size: 1rem;
    }

    .testimonial-swiper {
      .swiper-button-next,
      .swiper-button-prev {
        display: none;
      }
    }
  }

  .polygon-one,
  .polygon-two {
    display: none;
  }
}

@media (max-width: 576px) {
  .testmonial-content {
    padding: 1.5rem 1rem;
    border-radius: 1rem;

    .img-testmonial img {
      max-width: 150px;
    }

    .title-testmonial {
      font-size: 1.25rem;
    }

    p {
      font-size: 0.9rem;
    }
  }
}
</style>

<template>
  <section class="testimonials-section">
    <div class="container">
      <div class="row align-items-center">
        <!-- Left Side - Text Content -->
        <div class="col-lg-7">
          <div class="testimonials-content">
            <h2 class="testimonials-title">What they say</h2>
            <p class="testimonials-description">
              IEDUHUB has got more than 100k positive ratings from our users around the world.
            </p>
            <p class="testimonials-subdescription">
              Some of the students and teachers were greatly helped by the IEDUHUB
            </p>
            <Button variant="primary" size="lg" class="mt-3">
              Start now!
            </Button>
          </div>
        </div>
        
        <!-- Right Side - Swiper -->
        <div class="col-lg-5">
          <div class="testimonials-swiper-container">
            <swiper
              :modules="modules"
              :slides-per-view="1"
              :space-between="30"
              :loop="true"
              :navigation="true"
              class="testimonials-swiper"
            >
              <swiper-slide v-for="(testimonial, index) in testimonials" :key="index">
                <div class="testimonial-slide">
                  <div class="testimonial-image-container">
                    <img 
                      :src="testimonial.image" 
                      :alt="testimonial.name"
                      class="testimonial-image"
                    />
                    <div class="testimonial-card">
                      <div class="testimonial-quote">
                        "{{ testimonial.quote }}"
                      </div>
                      <div class="testimonial-stars">
                        <span v-for="star in 5" :key="star" class="star">★</span>
                      </div>
                      <div class="testimonial-name">{{ testimonial.name }}</div>
                      <div class="testimonial-reviews">{{ testimonial.reviews }}</div>
                    </div>
                  </div>
                </div>
              </swiper-slide>
            </swiper>
            
    
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Autoplay } from 'swiper/modules';
import Button from '../ui/Button.vue';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';

const modules = [Navigation, Autoplay];



const testimonials = reactive([
  {
    name: "Gloria Rose",
    quote: "Thank you so much for your help. It's exactly what I've been looking for. You won't regret it.",
    image: "/person.png",
    reviews: "12 reviews at Yelp"
  },
  {
    name: "Sarah Johnson",
    quote: "IEDUHUB has transformed how I manage my online courses. The interface is intuitive and the features are exactly what educators need.",
    image: "/person.png",
    reviews: "8 reviews at Google"
  },
  {
    name: "Michael Chen",
    quote: "As a teacher, I've tried many platforms, but IEDUHUB stands out for its simplicity and powerful features. Highly recommended!",
    image: "/person.png",
    reviews: "15 reviews at Trustpilot"
  },
  {
    name: "Emily Davis",
    quote: "The best educational platform I've used. It has everything I need to create engaging online learning experiences.",
    image: "/person.png",
    reviews: "6 reviews at Facebook"
  }
]);
</script>

<style scoped>
.testimonials-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f8f9ff 0%, #e8f2ff 100%);
  position: relative;
  overflow: hidden;
}

.testimonials-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: radial-gradient(circle, rgba(0, 123, 255, 0.1) 1px, transparent 1px);
  background-size: 20px 20px;
  opacity: 0.3;
}

.testimonials-content {
  position: relative;
  z-index: 2;
  padding: 2rem 0;
}

.testimonials-title {
  font-size: 2.5rem;
  font-weight: 600;
  color: black;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  letter-spacing: -0.02em;
}

.testimonials-description {
  font-size: 1.5rem;
  color: #4a5568;
  margin-bottom: 1rem;
  line-height: 1.6;
  font-weight: 400;
}

.testimonials-subdescription {
 font-size: 1.5rem;
  color: #4a5568;
  margin-bottom: 1rem;
  line-height: 1.6;
  font-weight: 400;
}

.testimonials-button {
  background: #1708FF;
  border: none;
  border-radius: 12px;
  padding: 1rem 2rem;
  font-size: 1.1rem;
  font-weight: 600;
  color: white;
  transition: all 0.3s ease;
}

.testimonials-button:hover {
  background: #0f06cc;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(23, 8, 255, 0.3);
}

.testimonials-swiper-container {
  position: relative;
  padding: 2rem 0;
}

.testimonials-swiper {
  width: 100%;
  height: 600px;
}

.testimonial-slide {
  height: 100%;
  display: flex;

}

.testimonial-image-container {
  position: relative;
  width: 80%;
  height: 100%;
  display: flex;
 
}

.testimonial-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.testimonial-card {
  position: absolute;
  bottom: 10px;
  right: -87px;
  background: white;
  border-radius: 16px;
  padding: 1.5rem;
  max-width: 500px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  z-index: 10;
  border-left: 10px solid #60b1dd;
}

.testimonial-quote {
  font-size: 1rem;
  color: #374151;
  line-height: 1.5;
  margin-bottom: 1rem;
  font-style: italic;
}

.testimonial-stars {
  margin-bottom: 0.8rem;
}

.star {
  color: #FFD700;
  font-size: 1.2rem;
  margin-right: 0.2rem;
}

.testimonial-name {
  font-size: 1.1rem;
  font-weight: 700;
  color: #1a365d;
  margin-bottom: 0.3rem;
}

.testimonial-reviews {
  font-size: 0.9rem;
  color: #6b7280;
  font-weight: 400;
}

.testimonials-nav-next {
  position: absolute;
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
  width: 50px;
  height: 50px;
  background: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  z-index: 20;
  transition: all 0.3s ease;
  border: none;
}

.testimonials-nav-next:hover {
  background: #417895;
  color: white;
  transform: translateY(-50%) scale(1.1);
}

.testimonials-nav-next i {
  font-size: 1.2rem;
  color: #417895;
  transition: color 0.3s ease;
}

.testimonials-nav-next:hover i {
  color: white;
}




/* Responsive Design */
@media (max-width: 992px) {
  .testimonials-title {
    font-size: 3rem;
  }
  
  .testimonials-swiper {
    height: 500px;
  }
  
  .testimonial-card {
    max-width: 250px;
    padding: 1.2rem;
    border-left: 4px solid #417895;
  }
}

@media (max-width: 768px) {
  .testimonials-section {
    padding: 3rem 0;
  }
  
  .testimonials-title {
    font-size: 2.5rem;
    text-align: center;
  }
  
  .testimonials-description,
  .testimonials-subdescription {
    text-align: center;
  }
  
  .testimonials-button {
    display: block;
    margin: 0 auto;
  }
  
  .testimonials-swiper {
    height: 450px;
  }
  
  .testimonial-card {
    max-width: 200px;
    padding: 1rem;
    bottom: 15px;
    right: 15px;
    border-left: 4px solid #1708FF;
  }
  
  .testimonial-quote {
    font-size: 0.9rem;
  }
  
  .testimonial-name {
    font-size: 1rem;
  }
  
  .testimonial-reviews {
    font-size: 0.8rem;
  }
  
  .testimonials-nav-next {
    width: 40px;
    height: 40px;
    right: 15px;
  }
  
  .testimonials-nav-next i {
    font-size: 1rem;
  }
  
  .swiper-button-next,
  .swiper-button-prev {
    width: 40px;
    height: 40px;
    font-size: 1rem;
  }
  
  .swiper-button-next {
    right: 15px;
  }
  
  .swiper-button-prev {
    display: none; /* Hide the previous button on mobile */
  }
}

@media (max-width: 576px) {
  .testimonials-title {
    font-size: 2rem;
  }
  
  .testimonials-description {
    font-size: 1rem;
  }
  
  .testimonials-subdescription {
    font-size: 0.9rem;
  }
  
  .testimonials-swiper {
    height: 400px;
  }
  
  .testimonial-card {
    max-width: 180px;
    padding: 0.8rem;
    border-left: 4px solid #5a9fc4;
  }
  
  .testimonial-quote {
    font-size: 0.8rem;
  }
  
  .testimonial-name {
    font-size: 0.9rem;
  }
  
  .testimonial-reviews {
    font-size: 0.7rem;
  }
  
  .swiper-button-next,
  .swiper-button-prev {
    width: 35px;
    height: 35px;
    font-size: 0.9rem;
  }
  
  .swiper-button-next {
    right: 10px;
  }
  
  .swiper-button-prev {
    display: none; /* Hide the previous button on small screens */
  }
}
</style>

<template>
  <section class="pricing-section py-5">
    <div class="container-fluid px-5">
      <div class="row justify-content-center">
        <div class="col-lg-8 text-center">
          <!-- Header Section -->
          <div class="pricing-header mb-5">
            <h2 class="pricing-title display-4 fw-bold text-dark mb-3 lh-sm">Find The Right Plan For You</h2>
            <p class="pricing-subtitle fs-5 text-muted mb-0 lh-base">Our Flexible Subscription Plans Fits Small and Medium Businesses</p>
          </div>

          <!-- Subscription Toggle -->
          <div class="subscription-toggle mb-4">
            <div class="toggle-container d-inline-flex bg-white rounded-pill p-1 border">
              <button 
                :class="['toggle-btn btn', { 'active': isMonthly }]"
                @click="toggleSubscription('monthly')"
              >
                Monthly
              </button>
              <button 
                :class="['toggle-btn btn', { 'active': !isMonthly }]"
                @click="toggleSubscription('yearly')"
              >
                Yearly
              </button>
            </div>
          </div>

          <!-- Pricing Cards -->
          <div class="row justify-content-center mt-5 g-4">
            <div 
              v-for="plan in pricingPlans" 
              :key="plan.id"
              class="col-lg-4 col-md-6 mb-4"
            >
              <div class="pricing-card card h-100 border-1">
                <div class="card-body p-4">
                  <h3 class="plan-title h4 fw-semibold text-primary mb-4">{{ plan.title }}</h3>
                  <div class="price-container mb-4 border-bottom">
                    <span class="price display-5 fw-bold text-dark">{{ plan.price }}$</span>
                    <span class="price-period fs-5 text-muted">/ Per Month</span>
                  </div>
                  <ul class="features-list list-unstyled mb-4 flex-grow-1">
                    <li 
                      v-for="feature in plan.features" 
                      :key="feature"
                      class="feature-item d-flex align-items-center justify-content-start mb-3 fs-5 text-dark"
                    >
                      <span class="checkmark text-primary fw-bold me-2 fs-4">✓</span>
                      {{ feature }}
                    </li>
                  </ul>
                </div>
                <Button 
                  :variant="plan.buttonVariant" 
                  class="plan-button w-100 rounded-0 rounded-bottom-4 mt-auto"
                >
                  {{ plan.buttonText }}
                </Button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'
import Button from '../ui/Button.vue'

const isMonthly = ref(true)

const toggleSubscription = (type: 'monthly' | 'yearly') => {
  isMonthly.value = type === 'monthly'
}

const pricingPlans = reactive([
  {
    id: 1,
    title: 'Regular Plan',
    price: 599,
    features: [
      'Website',
      'Domain free',
      'Interaction Sessions',
      '35 Classes',
      'Customizable Themes'
    ],
    buttonVariant: 'primary' as const,
    buttonText: 'Get You Free plan'
  },
  {
    id: 2,
    title: 'Medium Plan',
    price: 699,
    features: [
      'Website',
      'Domain free',
      'Interaction Sessions',
      '60 Classes',
      'Customizable Themes'
    ],
    buttonVariant: 'primary' as const,
    buttonText: 'Get You Free plan'
  },
  {
    id: 3,
    title: 'Premium Plan',
    price: 799,
    features: [
      'Website',
      'Domain free',
      'Interaction Sessions',
      '60 Classes',
      'Customizable Themes'
    ],
    buttonVariant: 'primary' as const,
    buttonText: 'Get You Free plan'
  }
])
</script>

<style scoped>
.pricing-section {
  padding: 5rem 0;
}

.toggle-container {
  border: 1px solid #cecece;
}

.toggle-btn {
  border: none;
  background: transparent;
  color: #6b7280;
  font-weight: 600;
  border-radius: 50px;
  transition: all 0.3s ease;
}

.toggle-btn.active {
  background-color: #1e40af;
  color: white;
}

.pricing-card {
  border-radius: 20px;
  border: 1px solid #cecece;
  transition: transform 0.3s ease;
  min-height: 500px;
  padding-bottom: 0 !important;
}

.pricing-card:hover {
  transform: translateY(-5px);
}

.plan-title {
  color: #1e40af;
}

.price {
  color: #374151;
}

.checkmark {
  color: #1e40af;
  font-weight: bold;
  margin-right: 0.5rem;
  font-size: 1.1rem;
}

.plan-button {
  border-radius: 0 0 20px 20px !important;
  border: none;
}

@media (max-width: 768px) {
  .pricing-card {
    min-height: 450px;
  }
}
</style>

<template>
  <section class="subscription-banner">
    <div class="banner-container">
      <!-- Decorative Elements -->
      <div class="decorative-elements">
        <!-- Backpack with book -->
        <div class="backpack-container">
          <img
            src="/assets/img/theme-four/bag.png"
            alt="Backpack"
            class="backpack-image"
          />
        </div>

        <!-- Geometric shapes -->
        <div class="geometric-shapes">
          <img
            src="/assets/img/theme-four/rectaangle.png"
            alt="Triangle"
            class="triangle-image"
          />
          <img
            src="/assets/img/theme-four/tool.png"
            alt="Protractor"
            class="protractor-image"
          />
        </div>
      </div>

      <!-- Main Content -->
      <div class="content-container">
        <h2 class="banner-title">
          A subscription that's<br />
          more than just classes
        </h2>
        <button class="subscription-button">Get Subscription</button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// No additional logic needed for this component
</script>

<style lang="scss" scoped>
.subscription-banner {
  padding: 4rem 0;
  background: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.banner-container {
  background: #0071dc;
  border-radius: 20px;
  padding: 3rem 2rem;
  max-width: 1200px;
  width: 100%;
  margin: 0 2rem;
  position: relative;
  overflow: hidden;
  min-height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.decorative-elements {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  pointer-events: none;
}

// Backpack with book
.backpack-container {
  position: absolute;
  bottom: 20px;
  left: 30px;
  z-index: 2;
}

.backpack-image {
  width: 80px;
  height: auto;
}

.triangle-image {
  width: 50px;
  height: auto;
}

.protractor-image {
  width: 40px;
  height: auto;
}

.backpack {
  position: relative;
  width: 60px;
  height: 80px;
}

.backpack-body {
  position: absolute;
  top: 0;
  left: 0;
  width: 50px;
  height: 70px;
  background: white;
  border-radius: 8px;
  border: 2px solid #e5e7eb;
}

.backpack-pocket {
  position: absolute;
  top: 10px;
  left: 5px;
  width: 40px;
  height: 25px;
  background: #f97316;
  border-radius: 4px;
}

.backpack-straps {
  position: absolute;
  top: -5px;
  left: 10px;
  width: 30px;
  height: 8px;
  background: #dc2626;
  border-radius: 4px;

  &::after {
    content: "";
    position: absolute;
    top: 15px;
    left: 0;
    width: 30px;
    height: 8px;
    background: #dc2626;
    border-radius: 4px;
  }
}

.book {
  position: absolute;
  top: -8px;
  left: 45px;
  width: 20px;
  height: 15px;
}

.book-cover {
  position: absolute;
  top: 0;
  left: 0;
  width: 20px;
  height: 15px;
  background: #dc2626;
  border-radius: 2px;
}

.book-pages {
  position: absolute;
  top: 1px;
  left: 1px;
  width: 18px;
  height: 13px;
  background: #fef3c7;
  border-radius: 1px;
}

// Paper airplane
.paper-airplane-container {
  position: absolute;
  top: 40%;
  left: 20%;
  z-index: 2;
}

.paper-airplane {
  position: relative;
  width: 30px;
  height: 20px;
}

.airplane-body {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 20px;
  height: 3px;
  background: white;
  border-radius: 2px;
}

.airplane-wing-left {
  position: absolute;
  top: 45%;
  left: 30%;
  width: 15px;
  height: 2px;
  background: white;
  transform: rotate(-20deg);
  border-radius: 1px;
}

.airplane-wing-right {
  position: absolute;
  top: 55%;
  left: 30%;
  width: 15px;
  height: 2px;
  background: white;
  transform: rotate(20deg);
  border-radius: 1px;
}

.airplane-trail {
  position: absolute;
  top: 50%;
  left: -20px;
  transform: translateY(-50%);
  display: flex;
  gap: 3px;
}

.trail-dot {
  width: 3px;
  height: 3px;
  background: white;
  border-radius: 50%;
  opacity: 0.7;

  &:nth-child(1) {
    opacity: 0.9;
  }
  &:nth-child(2) {
    opacity: 0.8;
  }
  &:nth-child(3) {
    opacity: 0.7;
  }
  &:nth-child(4) {
    opacity: 0.6;
  }
  &:nth-child(5) {
    opacity: 0.5;
  }
}

// Geometric shapes
.geometric-shapes {
  position: absolute;
  top: 20px;
  right: 30px;
  z-index: 2;
}

.triangle {
  position: relative;
  width: 40px;
  height: 35px;
  margin-bottom: 20px;
}

.triangle-outline {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
  border-bottom: 35px solid white;
  border-radius: 2px;
}

.triangle-lines {
  position: absolute;
  top: 5px;
  left: 5px;
  width: 30px;
  height: 25px;
}

.line {
  position: absolute;
  width: 30px;
  height: 1px;
  background: white;
  opacity: 0.8;

  &:nth-child(1) {
    top: 5px;
  }
  &:nth-child(2) {
    top: 10px;
  }
  &:nth-child(3) {
    top: 15px;
  }
  &:nth-child(4) {
    top: 20px;
  }
}

.protractor {
  position: relative;
  width: 30px;
  height: 15px;
}

.protractor-body {
  position: absolute;
  top: 0;
  left: 0;
  width: 30px;
  height: 15px;
  background: #8b5cf6;
  border-radius: 15px 15px 0 0;
  border: 2px solid white;
}

.protractor-markings {
  position: absolute;
  top: 2px;
  left: 2px;
  width: 26px;
  height: 11px;
}

.marking {
  position: absolute;
  width: 1px;
  height: 3px;
  background: white;
  top: 0;

  &:nth-child(1) {
    left: 2px;
  }
  &:nth-child(2) {
    left: 6px;
  }
  &:nth-child(3) {
    left: 10px;
  }
  &:nth-child(4) {
    left: 14px;
  }
  &:nth-child(5) {
    left: 18px;
  }
  &:nth-child(6) {
    left: 22px;
  }
  &:nth-child(7) {
    left: 24px;
  }
  &:nth-child(8) {
    left: 26px;
  }
}

// Main content
.content-container {
  position: relative;
  z-index: 3;
  text-align: center;
  max-width: 600px;
}

.banner-title {
  color: white;
  font-size: 2.5rem;
  font-weight: 600;
  line-height: 1.3;
  margin: 0 0 2rem 0;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.subscription-button {
  background: white;
  color: #1f2937;
  border: none;
  padding: 1rem 2rem;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
  }

  &:active {
    transform: translateY(0);
  }
}

// Responsive Design
@media (max-width: 1200px) {
  .banner-container {
    margin: 0 1.5rem;
    padding: 2.5rem 1.5rem;
  }

  .banner-title {
    font-size: 2.2rem;
  }
}

@media (max-width: 992px) {
  .banner-container {
    margin: 0 1rem;
    padding: 2rem 1rem;
    min-height: 250px;
  }

  .banner-title {
    font-size: 2rem;
  }

  .backpack-container {
    left: 20px;
    bottom: 15px;
  }

  .backpack {
    width: 50px;
    height: 65px;
  }

  .backpack-body {
    width: 40px;
    height: 55px;
  }

  .geometric-shapes {
    right: 20px;
    top: 15px;
  }

  .triangle {
    width: 35px;
    height: 30px;
    margin-bottom: 15px;
  }

  .protractor {
    width: 25px;
    height: 12px;
  }
}

@media (max-width: 768px) {
  .subscription-banner {
    padding: 2rem 0;
  }

  .banner-container {
    margin: 0 0.5rem;
    padding: 1.5rem 1rem;
    min-height: 200px;
  }

  .banner-title {
    font-size: 1.75rem;
    margin-bottom: 1.5rem;
  }

  .subscription-button {
    padding: 0.875rem 1.5rem;
    font-size: 1rem;
  }

  .backpack-container {
    left: 15px;
    bottom: 10px;
  }

  .backpack {
    width: 40px;
    height: 50px;
  }

  .backpack-body {
    width: 30px;
    height: 40px;
  }

  .backpack-pocket {
    width: 25px;
    height: 18px;
    top: 8px;
    left: 3px;
  }

  .book {
    width: 15px;
    height: 12px;
    top: -6px;
    left: 35px;
  }

  .book-cover {
    width: 15px;
    height: 12px;
  }

  .book-pages {
    width: 13px;
    height: 10px;
  }

  .paper-airplane-container {
    left: 15%;
  }

  .paper-airplane {
    width: 25px;
    height: 15px;
  }

  .airplane-body {
    width: 15px;
    height: 2px;
  }

  .airplane-wing-left,
  .airplane-wing-right {
    width: 12px;
    height: 1px;
  }

  .geometric-shapes {
    right: 15px;
    top: 10px;
  }

  .triangle {
    width: 25px;
    height: 20px;
    margin-bottom: 12px;
  }

  .triangle-outline {
    border-left: 12px solid transparent;
    border-right: 12px solid transparent;
    border-bottom: 20px solid white;
  }

  .triangle-lines {
    width: 20px;
    height: 15px;
    top: 3px;
    left: 3px;
  }

  .line {
    width: 20px;
  }

  .protractor {
    width: 20px;
    height: 10px;
  }

  .protractor-body {
    width: 20px;
    height: 10px;
    border-radius: 10px 10px 0 0;
  }
}

@media (max-width: 576px) {
  .banner-container {
    margin: 0 0.25rem;
    padding: 1.25rem 0.75rem;
    min-height: 180px;
  }

  .banner-title {
    font-size: 1.5rem;
    margin-bottom: 1.25rem;
  }

  .subscription-button {
    padding: 0.75rem 1.25rem;
    font-size: 0.95rem;
  }

  .backpack-container {
    left: 10px;
    bottom: 8px;
  }

  .backpack-image {
    width: 40px;
  }

  .triangle-image {
    width: 30px;
  }

  .protractor-image {
    width: 20px;
  }

  .backpack {
    width: 30px;
    height: 40px;
  }

  .backpack-body {
    width: 22px;
    height: 32px;
  }

  .backpack-pocket {
    width: 18px;
    height: 14px;
    top: 6px;
    left: 2px;
  }

  .backpack-straps {
    width: 20px;
    height: 6px;
    top: -4px;
    left: 5px;

    &::after {
      width: 20px;
      height: 6px;
      top: 12px;
    }
  }

  .book {
    width: 12px;
    height: 10px;
    top: -5px;
    left: 28px;
  }

  .book-cover {
    width: 12px;
    height: 10px;
  }

  .book-pages {
    width: 10px;
    height: 8px;
  }

  .paper-airplane-container {
    left: 10%;
  }

  .paper-airplane {
    width: 20px;
    height: 12px;
  }

  .airplane-body {
    width: 12px;
    height: 2px;
  }

  .airplane-wing-left,
  .airplane-wing-right {
    width: 10px;
    height: 1px;
  }

  .airplane-trail {
    left: -15px;
    gap: 2px;
  }

  .trail-dot {
    width: 2px;
    height: 2px;
  }

  .geometric-shapes {
    right: 10px;
    top: 8px;
  }

  .triangle {
    width: 20px;
    height: 16px;
    margin-bottom: 10px;
  }

  .triangle-outline {
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    border-bottom: 16px solid white;
  }

  .triangle-lines {
    width: 15px;
    height: 12px;
    top: 2px;
    left: 2px;
  }

  .line {
    width: 15px;
    height: 1px;
  }

  .protractor {
    width: 16px;
    height: 8px;
  }

  .protractor-body {
    width: 16px;
    height: 8px;
    border-radius: 8px 8px 0 0;
  }

  .protractor-markings {
    width: 12px;
    height: 6px;
    top: 1px;
    left: 1px;
  }

  .marking {
    width: 1px;
    height: 2px;
  }
}
</style>

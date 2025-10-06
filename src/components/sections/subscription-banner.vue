<template>
  <section class="subscription-banner">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <div class="banner-content">
            <!-- Educational Illustrations -->
            <div class="illustrations">
              <!-- Backpack and Book -->
              <div class="backpack-illustration">
                <div class="backpack">
                  <div class="backpack-body"></div>
                  <div class="backpack-strap"></div>
                  <div class="book">
                    <div class="book-cover"></div>
                    <div class="book-pages"></div>
                  </div>
                </div>
              </div>

              <!-- Paper Airplane -->
              <div class="airplane-illustration">
                <div class="paper-airplane"></div>
                <div class="flight-path"></div>
              </div>

              <!-- Geometric Prism -->
              <div class="prism-illustration">
                <div class="geometric-prism">
                  <div class="prism-face front"></div>
                  <div class="prism-face back"></div>
                  <div class="prism-face left"></div>
                  <div class="prism-face right"></div>
                  <div class="prism-face top"></div>
                  <div class="prism-face bottom"></div>
                </div>
              </div>

              <!-- Protractor -->
              <div class="protractor-illustration">
                <div class="protractor"></div>
              </div>
            </div>

            <!-- Main Content -->
            <div class="banner-main">
              <h2 class="banner-title">
                A subscription that's<br />
                more than just classes
              </h2>
              <button class="subscription-btn">Get Subscription</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SubscriptionBanner",
};
</script>

<style lang="scss" scoped>
.subscription-banner {
  padding: 80px 0;
  position: relative;
  overflow: hidden;
}

.subscription-banner .container {
  background: #007bff;
  border-radius: 20px;
  padding: 60px 40px;
  position: relative;
  overflow: hidden;
  box-shadow: 0 10px 40px rgba(0, 123, 255, 0.2);
}

.banner-content {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 300px;
  z-index: 2;
}

.illustrations {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}

// Backpack and Book Illustration
.backpack-illustration {
  position: absolute;
  left: 5%;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1;
}

.backpack {
  position: relative;
  width: 60px;
  height: 80px;

  .backpack-body {
    width: 50px;
    height: 70px;
    background: white;
    border-radius: 8px;
    position: relative;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);

    &::before {
      content: "";
      position: absolute;
      top: 10px;
      left: 5px;
      width: 8px;
      height: 8px;
      background: #ff6b35;
      border-radius: 50%;
    }

    &::after {
      content: "";
      position: absolute;
      top: 10px;
      right: 5px;
      width: 8px;
      height: 8px;
      background: #ff6b35;
      border-radius: 50%;
    }
  }

  .backpack-strap {
    position: absolute;
    top: -5px;
    left: 15px;
    width: 20px;
    height: 15px;
    border: 2px solid white;
    border-bottom: none;
    border-radius: 10px 10px 0 0;
  }

  .book {
    position: absolute;
    top: -15px;
    left: 10px;
    width: 30px;
    height: 20px;

    .book-cover {
      width: 30px;
      height: 20px;
      background: #dc3545;
      border-radius: 2px;
      position: relative;
      z-index: 2;
    }

    .book-pages {
      position: absolute;
      top: 2px;
      left: 2px;
      width: 26px;
      height: 16px;
      background: #f8f9fa;
      border-radius: 1px;
      z-index: 1;
    }
  }
}

// Paper Airplane Illustration
.airplane-illustration {
  position: absolute;
  left: 15%;
  top: 30%;
  z-index: 1;
}

.paper-airplane {
  width: 0;
  height: 0;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  border-bottom: 20px solid white;
  transform: rotate(45deg);
  position: relative;

  &::before {
    content: "";
    position: absolute;
    top: 5px;
    left: -8px;
    width: 0;
    height: 0;
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-bottom: 12px solid white;
    transform: rotate(90deg);
  }
}

.flight-path {
  position: absolute;
  top: 25px;
  left: -20px;
  width: 40px;
  height: 2px;
  background: repeating-linear-gradient(
    to right,
    white 0px,
    white 4px,
    transparent 4px,
    transparent 8px
  );
  transform: rotate(15deg);
}

// Geometric Prism Illustration
.prism-illustration {
  position: absolute;
  right: 15%;
  top: 20%;
  z-index: 1;
}

.geometric-prism {
  position: relative;
  width: 40px;
  height: 30px;
  transform-style: preserve-3d;
  transform: rotateX(20deg) rotateY(30deg);

  .prism-face {
    position: absolute;
    border: 2px solid white;
    background: transparent;

    &.front {
      width: 40px;
      height: 30px;
      transform: translateZ(15px);
    }

    &.back {
      width: 40px;
      height: 30px;
      transform: translateZ(-15px) rotateY(180deg);
    }

    &.left {
      width: 30px;
      height: 30px;
      transform: rotateY(-90deg) translateZ(15px);
      background: repeating-linear-gradient(
        45deg,
        white 0px,
        white 1px,
        transparent 1px,
        transparent 3px
      );
    }

    &.right {
      width: 30px;
      height: 30px;
      transform: rotateY(90deg) translateZ(15px);
      background: repeating-linear-gradient(
        45deg,
        white 0px,
        white 1px,
        transparent 1px,
        transparent 3px
      );
    }

    &.top {
      width: 40px;
      height: 30px;
      transform: rotateX(90deg) translateZ(15px);
    }

    &.bottom {
      width: 40px;
      height: 30px;
      transform: rotateX(-90deg) translateZ(15px);
    }
  }
}

// Protractor Illustration
.protractor-illustration {
  position: absolute;
  right: 8%;
  top: 60%;
  z-index: 1;
}

.protractor {
  width: 50px;
  height: 25px;
  background: #6f42c1;
  border-radius: 25px 25px 0 0;
  position: relative;
  border: 2px solid #6f42c1;

  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 25px 25px 0 0;
    background: repeating-linear-gradient(
      0deg,
      transparent 0px,
      transparent 2px,
      white 2px,
      white 3px
    );
  }

  &::after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    width: 2px;
    height: 20px;
    background: white;
    transform: translate(-50%, -50%);
  }
}

// Main Content
.banner-main {
  text-align: center;
  z-index: 3;
  position: relative;
}

.banner-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: white;
  margin-bottom: 30px;
  line-height: 1.2;

  @media (max-width: 768px) {
    font-size: 2rem;
  }

  @media (max-width: 576px) {
    font-size: 1.5rem;
  }
}

.subscription-btn {
  background: white;
  color: #2c3e50;
  border: none;
  padding: 15px 30px;
  font-size: 1.1rem;
  font-weight: 600;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: none;

  &:hover {
    background: #f8f9fa;
    transform: translateY(-2px);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  }

  &:active {
    transform: translateY(0);
  }
}

// Responsive Design
@media (max-width: 992px) {
  .illustrations {
    .backpack-illustration {
      left: 3%;
    }

    .airplane-illustration {
      left: 12%;
    }

    .prism-illustration {
      right: 12%;
    }

    .protractor-illustration {
      right: 5%;
    }
  }
}

@media (max-width: 768px) {
  .subscription-banner {
    padding: 60px 0;
  }

  .subscription-banner .container {
    padding: 40px 30px;
    border-radius: 15px;
  }

  .banner-content {
    min-height: 250px;
  }

  .illustrations {
    opacity: 0.7;
  }

  .backpack {
    width: 45px;
    height: 60px;

    .backpack-body {
      width: 35px;
      height: 50px;
    }

    .book {
      width: 25px;
      height: 15px;

      .book-cover {
        width: 25px;
        height: 15px;
      }

      .book-pages {
        width: 21px;
        height: 11px;
      }
    }
  }

  .paper-airplane {
    border-left: 12px solid transparent;
    border-right: 12px solid transparent;
    border-bottom: 16px solid white;
  }

  .geometric-prism {
    width: 30px;
    height: 22px;
  }

  .protractor {
    width: 40px;
    height: 20px;
  }
}

@media (max-width: 576px) {
  .subscription-banner .container {
    padding: 30px 20px;
    border-radius: 12px;
  }

  .illustrations {
    display: none;
  }

  .banner-main {
    padding: 0 20px;
  }
}
</style>

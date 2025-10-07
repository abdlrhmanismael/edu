<template>
  <section class="mentors-section py-5">
    <div class="container">
      <div class="text-center mb-5">
        <h2 class="section-title">
          Our Top Mentors
          <div class="title-underline"></div>
        </h2>
      </div>

      <div class="row g-4 justify-content-center">
        <div
          v-for="mentor in mentors"
          :key="mentor.id"
          class="col-lg-4 col-md-6"
        >
          <div class="mentor-card">
            <div>
              <div class="mentor-image-wrapper">
                <img
                  :src="mentor.image"
                  :alt="mentor.name"
                  class="mentor-image"
                />
              </div>
              <div class="mentor-info">
                <h3 class="mentor-name">{{ mentor.name }}</h3>
                <p class="mentor-specialty">{{ mentor.specialty }}</p>
                <button class="share-btn" @click="shareMentor(mentor)">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="18"
                    height="18"
                    fill="currentColor"
                    viewBox="0 0 16 16"
                  >
                    <path
                      d="M13.5 1a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3zM11 2.5a2.5 2.5 0 1 1 .603 1.628l-6.718 3.12a2.499 2.499 0 0 1 0 1.504l6.718 3.12a2.5 2.5 0 1 1-.488.876l-6.718-3.12a2.5 2.5 0 1 1 0-3.256l6.718-3.12A2.5 2.5 0 0 1 11 2.5zm-8.5 4a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3zm11 5.5a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3z"
                    />
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const mentors = ref([
  {
    id: 1,
    name: "Md. Yousuf Jayen",
    specialty: "Mentor, Tazweed",
    image: "/public/person.png",
  },
  {
    id: 2,
    name: "Md. Zakir Hasan",
    specialty: "Mentor, Tafseer",
    image: "/public/person.png",
  },
  {
    id: 3,
    name: "Md. Abu Bakr",
    specialty: "Mentor, Aracbic",
    image: "/public/person.png",
  },
]);

const shareMentor = (mentor) => {
  console.log("Share mentor:", mentor.name);
  // Add share functionality here
};
</script>

<style scoped>
.mentors-section {
  background: #ffffff;
  padding: 80px 0;
}

.section-title {
  font-size: 2.75rem;
  font-weight: 700;
  color: #0a1f44;
  margin-bottom: 0;
  position: relative;
  display: inline-block;
}

.title-underline {
  width: 180px;
  height: 4px;
  background: linear-gradient(90deg, #ffc107 0%, #ffb300 100%);
  margin: 12px auto 0;
  border-radius: 2px;
  position: relative;
}

.title-underline::after {
  content: "";
  position: absolute;
  width: 60%;
  height: 3px;
  background: rgba(255, 193, 7, 0.3);
  bottom: -6px;
  left: 20%;
  border-radius: 2px;
}

.mentor-card {
  transition: all 0.3s ease;
}

.mentor-card:hover {
  transform: translateY(-8px);
}

.card-background {
  background: linear-gradient(135deg, #a8d8ea 0%, #87ceeb 100%);
  border-radius: 30px;
  padding: 30px 30px 0;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.mentor-card:hover .card-background {
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
}

.mentor-image-wrapper {
  position: relative;
  overflow: hidden;
  border-radius: 25px 25px 0 0;
}

.mentor-image {
  width: 100%;
  height: 400px;
  object-fit: cover;
  display: block;
  border-radius: 25px;
}

.mentor-info {
  position: relative;
  padding: 24px 28px;
  background: white;
  margin-top: -15px;
  margin-left: auto;
  margin-right: auto;
  width: 80%;
  text-align: center;
}

.mentor-name {
  font-size: 1.35rem;
  font-weight: 700;
  color: #0a1f44;
  margin-bottom: 6px;
  margin-top: 0;
}

.mentor-specialty {
  font-size: 1rem;
  color: #666;
  margin-bottom: 0;
  font-weight: 400;
}

.share-btn {
  position: absolute;
  bottom: 81px;
  right: 28px;
  width: 48px;
  height: 48px;
  background: #00bfa5;
  border: none;
  border-radius: 50%;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0, 191, 165, 0.3);
}

.share-btn:hover {
  background: #00a690;
  transform: scale(1.1);
  box-shadow: 0 6px 16px rgba(0, 191, 165, 0.4);
}

.share-btn:active {
  transform: scale(0.95);
}

/* Responsive Design */
@media (max-width: 991px) {
  .section-title {
    font-size: 2.25rem;
  }

  .mentor-image {
    height: 370px;
  }

  .card-background {
    padding: 25px 25px 0;
  }
}

@media (max-width: 767px) {
  .section-title {
    font-size: 2rem;
  }

  .mentor-image {
    height: 340px;
  }

  .card-background {
    padding: 20px 20px 0;
    border-radius: 25px;
  }

  .mentor-info {
    padding: 20px 24px;
  }

  .mentor-name {
    font-size: 1.2rem;
  }

  .share-btn {
    width: 44px;
    height: 44px;
    bottom: 20px;
    right: 24px;
  }
}

@media (max-width: 576px) {
  .mentors-section {
    padding: 60px 0;
  }

  .section-title {
    font-size: 1.75rem;
  }

  .title-underline {
    width: 140px;
  }

  .mentor-image {
    height: 300px;
  }

  .card-background {
    padding: 18px 18px 0;
    border-radius: 22px;
  }

  .mentor-info {
    padding: 18px 20px;
    width: 85%;
  }

  .mentor-name {
    font-size: 1.1rem;
  }

  .mentor-specialty {
    font-size: 0.95rem;
  }

  .share-btn {
    width: 42px;
    height: 42px;
    bottom: 18px;
    right: 20px;
  }
}
</style>

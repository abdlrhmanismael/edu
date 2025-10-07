<template>
  <section class="latest-articles-section">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <!-- Header -->
          <div class="articles-header">
            <h2 class="section-title">
              <span class="title-dark me-2">Latest</span>
              <span class="title-blue">Articles</span>
            </h2>
            <div class="title-underline"></div>
          </div>

          <!-- Articles Grid -->
          <div class="articles-grid">
            <div
              class="article-card"
              v-for="(article, index) in articles"
              :key="index"
            >
              <div class="article-image">
                <img :src="article.image" :alt="article.title" />
                <div class="date-overlay">
                  <div class="date-day">{{ article.date.day }}</div>
                  <div class="date-month">{{ article.date.month }}</div>
                </div>
              </div>
              <div class="article-content">
                <div class="article-meta">
                  <span class="author">BY {{ article.author }}</span>
                  <span class="separator"></span>
                  <span class="category">{{ article.category }}</span>
                </div>
                <h3 class="article-title">{{ article.title }}</h3>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "LatestArticles",
  data() {
    return {
      articles: [
        {
          image: "/assets/img/theme-four/hero_one.jpg",
          title: "How to Avoid the Biggest College Admission Mistakes",
          author: "DAVID CARTER",
          category: "LEARNING",
          date: {
            day: "23",
            month: "Oct",
          },
        },
        {
          image: "/assets/img/theme-four/hero_two.jpg",
          title: "How Digital Platforms Are Shaping Business Schools",
          author: "DAVID CARTER",
          category: "LEARNING",
          date: {
            day: "23",
            month: "Oct",
          },
        },
        {
          image: "/assets/img/theme-four/hero_three.jpg",
          title: "Why Business Students Need Tech Skills for the Future",
          author: "DAVID CARTER",
          category: "LEARNING",
          date: {
            day: "23",
            month: "Oct",
          },
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.latest-articles-section {
  padding: 80px 0;
  background: white;
}

.articles-header {
  text-align: center;
  margin-bottom: 60px;

  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 20px;
    line-height: 1.2;

    .title-dark {
      color: #2c3e50;
    }

    .title-blue {
      color: #007bff;
    }

    @media (max-width: 768px) {
      font-size: 2rem;
    }
  }

  .title-underline {
    width: 80px;
    height: 4px;
    background: linear-gradient(90deg, #ffd700 0%, #ffa500 100%);
    border-radius: 2px;
    margin: 0 auto;
    position: relative;

    &::after {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, #ffd700 0%, #ffa500 100%);
      border-radius: 2px;
      transform: scaleX(1.2);
      transform-origin: center;
    }
  }
}

.articles-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;

  @media (max-width: 992px) {
    grid-template-columns: repeat(2, 1fr);
    gap: 25px;
  }

  @media (max-width: 768px) {
    grid-template-columns: 1fr;
    gap: 20px;
  }
}

.article-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;

  &:hover {
    transform: translateY(-5px);
  }
}

.article-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  &:hover img {
    transform: scale(1.05);
  }

  .date-overlay {
    position: absolute;
    top: 15px;
    left: 15px;
    width: 50px;
    height: 50px;
    background: #007bff;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: bold;

    .date-day {
      font-size: 1.1rem;
      line-height: 1;
      margin-bottom: 2px;
    }

    .date-month {
      font-size: 0.7rem;
      line-height: 1;
      text-transform: uppercase;
    }
  }
}

.article-content {
  padding: 25px 0;

  .article-meta {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
    font-size: 0.85rem;
    color: #6c757d;
    text-transform: uppercase;
    letter-spacing: 0.5px;

    .author {
      font-weight: 500;
    }

    .separator {
      width: 8px;
      height: 8px;
      background: #007bff;
      margin: 0 10px;
      border-radius: 50%;
    }

    .category {
      font-weight: 500;
    }
  }

  .article-title {
    font-size: 1.2rem;
    font-weight: 700;
    color: #2c3e50;
    line-height: 1.4;
    margin: 0;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;

    @media (max-width: 768px) {
      font-size: 1.1rem;
    }
  }
}

// Responsive adjustments
@media (max-width: 1200px) {
  .articles-grid {
    gap: 25px;
  }
}

@media (max-width: 768px) {
  .latest-articles-section {
    padding: 60px 0;
  }

  .articles-header {
    margin-bottom: 40px;
  }

  .article-image {
    height: 220px;
  }

  .article-content {
    padding: 20px 15px;
  }
}
</style>

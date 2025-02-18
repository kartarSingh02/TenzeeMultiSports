<template>
  <div class="carousel-container">
    <section class="position-relative">
      <div id="heroCarousel" class="carousel slide carousel-fade h-100" data-bs-ride="carousel">
        <div class="carousel-inner h-100">
          <div
              v-for="(slide, index) in slides"
              :key="slide.id"
              class="carousel-item h-100"
              :class="{ active: index === 0 }"
              :data-bs-interval="3000"
          >
            <img
                :src="slide.image"
                :alt="slide.alt"
                class="d-block w-100 h-100 object-fit-cover"
                loading="lazy"
            >
            <div class="carousel-caption d-flex align-items-center h-100">
              <div class="container">
                <div class="row">
                  <div class="col-12 col-md-8 col-lg-6">
                    <div class="text-start">
                      <h1 class="display-3 fw-bold text-uppercase animate-slideIn">
                        Strong, Fit
                        <br>
                        Unstoppable.
                      </h1>
                      <p class="lead animate-fadeInUp">
                        Transform your body, elevate your mind, and push beyond your limits.
                        <br>
                        Join us on a journey to becoming the strongest version of yourself.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Carousel Controls -->
        <button class="carousel-control-prev" type="button" data-bs-target="#heroCarousel" data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#heroCarousel" data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </section>
  <Overview />
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import Overview from "@/components/home/Overview.vue";

const slides = [
  {
    id: 1,
    image: '/src/assets/images/hero-1.jpeg',
    alt: 'Fitness Training 1',
  },
  {
    id: 2,
    image: '/src/assets/images/hero-2.jpeg',
    alt: 'Fitness Training 2',
  },
  {
    id: 3,
    image: '/src/assets/images/hero-3.jpeg',
    alt: 'Fitness Training 3',
  }
]

onMounted(() => {
  // Bootstrap's carousel will handle the automatic sliding
})
</script>

<style scoped>
/* Carousel base styles */
.carousel,
.carousel-inner,
.carousel-item {
  min-height: 70vh;
}

.carousel-item {
  transition: transform 1.2s ease-in-out;
}

.carousel-caption {
  background: rgba(0, 0, 0, 0.5);
  right: 0;
  bottom: 0;
  left: 0;
  padding-bottom: 0;
  text-align: left;
}

/* Animations */
@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateX(-30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slideIn {
  animation: slideIn 0.3s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

.animate-fadeInUp {
  animation: fadeInUp 0.3s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-delay: 0.3s;
  opacity: 0;
}

@media (max-width: 768px) {
  .carousel-item img {
    min-height: 70vh;
    object-fit: cover;
  }

  .display-3 {
    font-size: 2.5rem;
  }

  .lead {
    font-size: 1.125rem;
  }
}
</style>
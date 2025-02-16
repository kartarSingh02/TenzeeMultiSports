<template>
  <div class="slider-container">
    <section class="relative h-screen">
      <div class="card bg-dark text-white mx-auto" style="max-width: 100%;">
        <!-- Sliding Background Images -->
        <transition-group
            name="slide"
            tag="div"
            class="relative h-screen"
            style="overflow: hidden;"
        >
          <div
              v-for="(slide, index) in slides"
              :key="slide.id"
              v-show="currentSlide === index"
              class="absolute inset-0 w-full h-full"
              style="transform-origin: center center;"
          >
            <img
                :src="slide.image"
                :alt="slide.alt"
                class="card-img w-full h-full object-cover object-center"
                loading="lazy"
            >
          </div>
        </transition-group>

        <div class="card-img-overlay" style="background-color: rgba(0, 0, 0, 0.5)">
          <div class="max-w-3xl mt-60">
            <h1 class="card-title text-5xl md:text-7xl font-bold leading-tight animate-slideIn">
              STRONG, FIT
              <br />
              UNSTOPPABLE.
            </h1>
            <p class="card-text animate-fadeInUp">
              Transform your body, elevate your mind, and push beyond your limits.
              <br>
              Join us on a journey to becoming the strongest version of yourself.
            </p>
          </div>
        </div>
      </div>
    </section>
    <TeamPhoto class="relative z-10" />
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import TeamPhoto from "@/components/home/TeamPhoto.vue";

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

const currentSlide = ref(0)
let intervalId = null

const setSlide = (index) => {
  currentSlide.value = index
  resetInterval()
}

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const resetInterval = () => {
  if (intervalId) clearInterval(intervalId)
  startSlideshow()
}

const startSlideshow = () => {
  intervalId = setInterval(nextSlide, 5000)
}

onMounted(() => {
  startSlideshow()
})

onBeforeUnmount(() => {
  if (intervalId) clearInterval(intervalId)
})
</script>

<style scoped>
.slider-container {
  position: relative;
}

.slide-enter-active,
.slide-leave-active {
  position: absolute;
  transition: transform 0.5s ease-in-out;
  width: 100%;
  height: 100%;
}

.slide-enter-from {
  transform: translateX(100%);
}

.slide-leave-to {
  transform: translateX(-100%);
}

.card {
  position: relative;
  height: 100%;
}

.card-img {
  width: 100%;
  height: 100%;
  min-height: 100vh;
  object-fit: cover;
}

.card-img-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 2rem;
}

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
  animation: slideIn 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

.animate-fadeInUp {
  animation: fadeInUp 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-delay: 0.3s;
  opacity: 0;
}

.card-title{
  margin-top:40%;
  font-size: 60px;
  font-weight: bold;
}

.card-text{
  font-size: 16px
}

@media (max-width: 768px) {
  .card-img-overlay {
    padding: 1rem;
  }

  h1 {
    font-size: 2.5rem;
  }

  p {
    font-size: 1.125rem;
  }
}
</style>
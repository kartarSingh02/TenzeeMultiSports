<template>
  <div class="container-fluid bg-dark py-5 container mx-auto px-4">
    <div class="row g-4">
      <!-- Left Column (unchanged) -->
      <div class="col-lg-6 px-4">
        <div class="position-relative mb-4">
          <h1 class="display-4 text-white fw-bold">
            <span class="text-white-50">PROGRAMS</span><br/>
            POWERFUL<br/>
            WORKOUTS, UNLEASH<br/>
            YOUR POTENTIAL
          </h1>
        </div>

        <p class="text-white-50 mb-4">
          These are some of the interesting features that we offer to all our members
        </p>

        <ul class="features-list list-unstyled mb-4">
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Strengthen And Conditioning program</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Mixed Martial Arts</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Wall Climbing</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Football</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Olympic Weightlifting</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Certified Trainers</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Performance Tracking</span>
          </li>
          <li class="mb-3">
            <span class="dot me-3"></span>
            <span class="text-white">Personal Training</span>
          </li>
        </ul>

        <a href="https://fc.one/Tenzee-multisports" target="_blank" rel="noopener noreferrer"
           class="btn btn-outline-warning rounded-pill px-4 py-2">
          Book Now <i class="bi bi-arrow-right ms-2"></i>
        </a>
      </div>

      <div class="col-lg-6">
        <div class="row g-4">
          <div class="col-12">
            <div class="card bg-dark text-white border-0 animate-card animate-from-top">
              <div class="row g-0">
                <div class="col-md-6">
                  <img src="/src/assets/images/WallClimbing-1.jpeg" alt="Weight Loss Training"
                       class="img-fluid h-100 object-fit-cover" />
                </div>
                <div class="col-md-6">
                  <img src="/src/assets/images/BoxingRing.jpeg" alt="Weight Loss Training"
                       class="img-fluid h-100 object-fit-cover" />
                </div>
              </div>
            </div>
          </div>

          <div class="col-12">
            <div class="card bg-warning text-dark border-0 animate-card animate-from-bottom">
              <div class="row g-0">
                <div class="col-md-6 p-4">
                  <div class="card-body">
                    <h6 class="text-dark mb-2">TRAINING</h6>
                    <h2 class="card-title mb-3">Training Plan</h2>
                    <p class="card-text">
                      Strength and Conditioning
                      program is designed to enhance
                      your overall physical performance.
                      Whether you're an athlete looking
                      to improve your game or someone
                      seeking a healthier lifestyle, our
                      tailored workouts will help you
                      achieve peak performance.
                    </p>
                  </div>
                </div>
                <div class="col-md-6">
                  <img src="/src/assets/images/BoxingWoman.jpeg" alt="Training Plan"
                       class="img-fluid h-100 object-fit-cover" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <KidsProgram/>
</template>

<script setup>
import { onMounted } from 'vue';
import KidsProgram from "@/components/home/KidsProgram.vue";

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('show');
      }
    });
  }, {
    threshold: 0.1,
    rootMargin: '50px'
  });

  document.querySelectorAll('.animate-card').forEach((element) => {
    observer.observe(element);
  });
});
</script>

<style scoped>
.dot {
  display: inline-block;
  width: 8px;
  height: 8px;
  background-color: #ffc107;
  border-radius: 50%;
}

.animate-card {
  visibility: hidden;
  transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}

.animate-from-top {
  transform: translateY(-50px);
}

.animate-from-bottom {
  transform: translateY(50px);
}

.animate-card.show {
  visibility: visible;
  transform: translateY(0);
}
</style>
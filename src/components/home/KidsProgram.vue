<template>
  <div class="container-fluid text-white py-5" style="background-color: #111111">
    <div class="container mx-auto px-4">
      <div class="row mb-5 text-center">
        <div class="col-12">
          <h1 class="display-4 fw-bold">UNLOCK YOUR BEST SELF</h1>
          <h2 class="display-6">WITH OUR PROGRAMS</h2>
        </div>
      </div>

      <div class="row g-4">
        <div v-for="(program, index) in programs" :key="index" class="col-12 col-md-6 col-lg-3">
          <div class="card bg-dark border-0 rounded-xl">
            <div class="position-relative">
              <img :src="program.image" class="card-img-top" :alt="program.title">
              <div class="position-absolute top-0 start-0 p-3 d-flex gap-2">
              <span v-for="(tag, tagIndex) in program.tags"
                    :key="tagIndex"
                    class="badge text-bg-warning text-uppercase">
                {{ tag }}
              </span>
              </div>
            </div>
            <div class="card-body bg-light px-4 rounded-xl">
              <h5 class="card-title">{{ program.title }}</h5>
              <p class="card-text text-muted">{{ program.description }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="text-center mt-5">
        <a href="https://fc.one/Tenzee-multisports" target="_blank" rel="noopener noreferrer"
           class="btn btn-outline-warning rounded-pill px-5 py-2 fw-medium fs-6">
          Book Now
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const programs = ref([
  {
    title: 'Football',
    description: 'One-on-one coaching for maximum results',
    image: '/src/assets/images/FootballMan-2.jpeg',
    tags: ['Football', 'Stamina']
  },
  {
    title: 'Martial Arts',
    description: 'High-energy group workouts for all levels',
    image: '/src/assets/images/BoxingMan-1.jpeg',
    tags: ['Strength', 'Training']
  },
  {
    title: 'Wall Climbing',
    description: 'Structured classes for targeted fitness goals',
    image: '/src/assets/images/WallClimbing-3.jpeg',
    tags: ['Climbing', 'Gripping']
  },
  {
    title: 'Strength Training',
    description: 'Build strength and muscle with guidance',
    image: '/src/assets/images/GymView-2.jpeg',
    tags: ['Coaching', 'Strength']
  }
])
</script>

<style scoped>
.card {
  transition: transform 0.3s ease-in-out;
}

.card:hover {
  transform: translateY(-5px);
}

@media (min-width: 768px) {
  .card img {
    filter: grayscale(100%);
    transition: filter 0.3s ease-in-out;
  }

  .card:hover img {
    filter: grayscale(0%);
  }
}

.badge {
  font-size: 0.7rem;
  padding: 0.5em 1em;
}
</style>
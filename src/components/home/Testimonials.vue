<template>
  <div class="testimonials-section">
    <div class="overlay"></div>
    <div class="container position-relative px-4">
      <div class="row mb-5">
        <div class="col-12 text-center">
          <h1 class="testimonials-title">TESTIMONIALS</h1>
        </div>
      </div>

      <div class="row stats-row mb-5">
        <div class="col-md-3 col-sm-6 mb-4">
          <div class="stat-item text-center">
            <h2 class="counter">
              {{ animatedStats.members }}+
            </h2>
            <p>Active Members</p>
          </div>
        </div>
        <div class="col-md-3 col-sm-6 mb-4">
          <div class="stat-item text-center">
            <h2 class="counter">
              {{ animatedStats.trainers }}+
            </h2>
            <p>Expert Trainers</p>
          </div>
        </div>
        <div class="col-md-3 col-sm-6 mb-4">
          <div class="stat-item text-center">
            <h2 class="counter">
              {{ animatedStats.programs }}+
            </h2>
            <p>Fitness Programs</p>
          </div>
        </div>
        <div class="col-md-3 col-sm-6 mb-4">
          <div class="stat-item text-center">
            <h2 class="counter">
              {{ animatedStats.experience }}+
            </h2>
            <p>Years Experience</p>
          </div>
        </div>
      </div>

      <div class="row testimonials-row">
        <div class="col-md-6 mb-4" v-for="testimonial in testimonials" :key="testimonial.id">
          <div class="testimonial-card">
            <div class="testimonial-content">
              <div class="quote-marks">"</div>
              <p>{{ testimonial.text }}</p>
              <div class="testimonial-author">
                <img :src="testimonial.image" :alt="testimonial.name" class="author-img">
                <div class="author-info">
                  <h4>{{ testimonial.name }}</h4>
                  <p>{{ testimonial.title }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Define initial stats values
const finalStats = {
  members: 500,
  trainers: 15,
  programs: 20,
  experience: 10
}

// Initialize animated stats with zero values
const animatedStats = ref({
  members: 0,
  trainers: 0,
  programs: 0,
  experience: 0
})

// Track if animation has run
const hasAnimated = ref(false)

// Testimonials data
const testimonials = ref([
  {
    id: 1,
    name: 'Lisa',
    title: 'Member',
    text: 'I\'m so grateful for this gym. The trainers are incredible, always pushing me to new limits. The state-of-the-art facilities and diverse classes keep me motivated. It\'s a community that feels like family.',
    image: '/src/assets/images/GymView-2.jpeg'
  },
  {
    id: 2,
    name: 'Lisa',
    title: 'Member',
    text: 'I\'m so grateful for this gym. The trainers are incredible, always pushing me to new limits. The state-of-the-art facilities and diverse classes keep me motivated. It\'s a community that feels like family.',
    image: '/src/assets/images/GymView-2.jpeg'
  },
])

// Function to animate a single value
const animateValue = (start, end, duration, property) => {
  // Calculate animation parameters
  const range = end - start
  const minTimer = 30 // Faster minimum time between updates
  const stepTime = Math.abs(Math.floor(duration / range))
  const timerDelay = Math.max(stepTime, minTimer)
  let current = start

  // Step function for incremental updates
  const step = () => {
    current += 1
    animatedStats.value[property] = current

    if (current < end) {
      setTimeout(step, timerDelay)
    }
  }

  // Start the stepping process
  setTimeout(step, timerDelay)
}

// Function to start all animations
const startAnimation = () => {
  // Check if animation has already run
  if (hasAnimated.value) return

  // Set animation flag and start animations
  hasAnimated.value = true
  Object.keys(finalStats).forEach(key => {
    animateValue(0, finalStats[key], 1000, key)
  })
}

// Intersection Observer callback
const observerCallback = (entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting && !hasAnimated.value) {
      startAnimation()
      observer.disconnect() // Ensure observer is disconnected after first animation
    }
  })
}

// Initialize observer variable
let observer

// Setup on component mount
onMounted(() => {
  // Create new Intersection Observer
  observer = new IntersectionObserver(observerCallback, {
    threshold: 0.1 // Trigger when 10% of element is visible
  })

  // Find and observe the stats section
  const statsSection = document.querySelector('.stats-row')
  if (statsSection) {
    observer.observe(statsSection)
  }

  // Cleanup function (optional but recommended)
  return () => {
    if (observer) {
      observer.disconnect()
    }
  }
})
</script>

<style scoped>
.testimonials-section {
  position: relative;
  padding: 100px 0;
  background-size: cover;
  background-image: url("/src/assets/images/GymView-2.jpeg");
  background-position: center;
  background-attachment: fixed;
  color: white;
  min-height: 100vh;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(90deg, rgba(0,0,0,0.95) 0%, rgba(0,0,0,0.8) 50%, rgba(0,0,0,0.6) 100%);
}

.testimonials-title {
  font-size: 4rem;
  font-weight: 700;
  background: linear-gradient(to right, #ffd700, #FFA500);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.stat-item {
  padding: 20px;
}

.stat-item h2 {
  font-size: 3rem;
  font-weight: 700;
  color: #ffd700;
  margin-bottom: 10px;
}

.stat-item p {
  font-size: 1.2rem;
  color: #ffffff;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.testimonial-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 30px;
  height: 100%;
  transition: transform 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-5px);
}

.quote-marks {
  font-size: 4rem;
  color: #ffd700;
  line-height: 1;
  margin-bottom: -20px;
}

.testimonial-content p {
  font-size: 1.1rem;
  line-height: 1.6;
  margin: 20px 0;
}

.testimonial-author {
  display: flex;
  align-items: center;
  margin-top: 20px;
}

.author-img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
  margin-right: 15px;
  border: 2px solid #ffd700;
}

.author-info h4 {
  margin: 0;
  color: #ffd700;
  font-size: 1.2rem;
}

.author-info p {
  margin: 5px 0 0;
  font-size: 0.9rem;
  opacity: 0.8;
}

@media (max-width: 768px) {
  .testimonials-title {
    font-size: 3rem;
  }

  .stat-item h2 {
    font-size: 2.5rem;
  }

  .testimonial-card {
    margin-bottom: 20px;
  }
}
</style>
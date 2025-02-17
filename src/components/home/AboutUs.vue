<template>
  <div class="team-section">
    <div class="background-wrapper">
      <div class="background-image"></div>
    </div>
    <div class="content-wrapper">
      <div class="hero-text">
        <h1>UNLOCK YOUR FITNESS POTENTIAL</h1>
        <h1>WITH OUR TEAM</h1>
      </div>

      <div class="container py-5 px-4">
        <div class="row g-4">
          <div
              v-for="member in teamMembers"
              :key="member.id"
              class="col-lg-3 col-md-4 col-sm-6"
          >
            <div class="team-member">
              <img :src="member.image" :alt="member.name" class="team-img">
              <div class="member-info">
                <h4>{{ member.name }}</h4>
                <p>{{ member.position }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const teamMembers = ref([
  {
    id: 1,
    name: 'Gaurav Chinnivar',
    position: 'Founder',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 2,
    name: 'Manoj Kumar',
    position: 'S&C Head Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 3,
    name: 'Francis Xavier',
    position: 'Football Head Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 4,
    name: 'Rehan Khan',
    position: 'MMA Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 5,
    name: 'Kethan P',
    position: 'Climbing Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 6,
    name: 'Valerain Joel',
    position: 'Football Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 7,
    name: 'Madan Rao',
    position: 'S&C Coach',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
  {
    id: 8,
    name: 'Rohit Pathak',
    position: 'Facility Manager',
    image: '/src/assets/images/BoxingMan-1.jpeg',
  },
])
</script>

<style scoped>
.team-section {
  position: relative;
  min-height: 100vh;
  background-color: #000;
  overflow: hidden;
}

.background-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('/src/assets/images/WallClimbing-2.jpeg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  opacity: 0.3;
  filter: brightness(0.7);
}

.content-wrapper {
  position: relative;
  z-index: 2;
}

.hero-text {
  text-align: center;
  padding-top: 4rem;
  margin-bottom: 2rem;
}

.hero-text h1 {
  color: white;
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.2;
  text-transform: uppercase;
  margin: 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.container {
  position: relative;
}

.team-member {
  position: relative;
  margin-bottom: 30px;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.team-member:hover {
  transform: translateY(-5px);
}

.team-img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.team-member:hover .team-img {
  transform: scale(1.05);
}

.member-info {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.9), transparent);
  color: white;
  padding: 20px;
}

.member-info h4 {
  margin: 0;
  font-weight: bold;
  color: #ffd700;
  font-size: 1.2rem;
}

.member-info p {
  margin: 5px 0 0;
  font-size: 0.9rem;
  opacity: 0.9;
}
</style>
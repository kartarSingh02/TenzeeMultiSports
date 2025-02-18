<template>
  <div class="team-section">
    <div class="background-wrapper">
      <div class="background-image"></div>
    </div>
    <div class="content-wrapper">
      <div class="hero-content">
        <h1>South India's Biggest Indoor</h1>
        <h1>Wall Climbing Facility</h1>
        <p class="description">
          Experience the thrill of indoor climbing at our state-of-the-art facility.
          We offer world-class climbing walls, expert instruction, and a supportive
          community for climbers of all skill levels.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
// No script needed for this version
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
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-content {
  text-align: center;
  max-width: 800px;
  padding: 0 20px;
}

.hero-content h1 {
  color: white;
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.2;
  text-transform: uppercase;
  margin: 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.description {
  color: white;
  font-size: 1.2rem;
  margin-top: 2rem;
  line-height: 1.6;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}
</style>
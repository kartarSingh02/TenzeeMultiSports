<template>
  <div class="team-section">
    <div class="background-wrapper">
      <div class="background-image"></div>
    </div>
    <div class="content-wrapper">
      <div class="hero-content">
        <h1 class="main-title">Welcome to Tenzee Multisports</h1>
        <p class="tagline">Where fitness meets diversity in a state-of-the-art multisports facility</p>

        <div class="description">
          <h2 class="subtitle">What is Tenzee Multisports all about?</h2>
          <div class="features">
            <div class="feature-item">
              <h3>Expert Guidance</h3>
              <p>Benefit from the expertise of our professional trainers, coaches, and physiotherapists</p>
            </div>
            <div class="feature-item">
              <h3>Comprehensive Access</h3>
              <p>Full access to all facilities including gym, MMA arena, football fields, and climbing walls</p>
            </div>
            <div class="feature-item">
              <h3>State-of-the-Art Facilities</h3>
              <p>Train with the latest equipment in well-maintained environments</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
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
}

.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('/src/assets/images/team.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0.4;
  filter: brightness(0.7);
}

.content-wrapper {
  position: relative;
  z-index: 2;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
}

.hero-content {
  max-width: 1000px;
  text-align: center;
  color: white;
}

.main-title {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1rem;
  text-transform: uppercase;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.tagline {
  font-size: 1.5rem;
  margin-bottom: 3rem;
  color: #ffd700;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.subtitle {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  text-transform: uppercase;
  color: #fff;
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.feature-item {
  background: rgba(0, 0, 0, 0.6);
  padding: 1.5rem;
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.feature-item:hover {
  transform: translateY(-5px);
}

.feature-item h3 {
  color: #ffd700;
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
}

.feature-item p {
  font-size: 1rem;
  line-height: 1.5;
  opacity: 0.9;
}

@media (max-width: 768px) {
  .main-title {
    font-size: 2.5rem;
  }

  .tagline {
    font-size: 1.2rem;
  }

  .subtitle {
    font-size: 2rem;
  }

  .features {
    grid-template-columns: 1fr;
  }
}
</style>
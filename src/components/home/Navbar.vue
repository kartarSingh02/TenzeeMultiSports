<!-- components/navigation/NavBar.vue -->
<template>
  <nav class="navbar navbar-expand-lg fixed-top"
       :class="{ 'navbar-scrolled': isScrolled }">
    <div class="container">
      <!-- Brand -->
      <a class="navbar-brand" href="#">
        <img src="/src/assets/images/TenzeeMultiSportsLogo.png" alt="logo" width="52"
             height="52" >
      </a>

      <!-- Hamburger button for mobile -->
      <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Navbar links -->
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav mx-auto">
          <li v-for="(item, index) in navItems"
              :key="item.path"
              class="nav-item text-sm font-medium"
          >
            <a class="nav-link"
               :class="{ 'active': activeSection === item.path.substring(1) }"
               href="#"
               @click.prevent="scrollToSection(item.path)"
            >
              {{ item.name }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Navbar Data
const activeSection = ref('home')
const isScrolled = ref(false)

const navItems = [
  { name: 'Home', path: '#home' },
  { name: 'Programs', path: '#programs' },
  { name: 'About Us', path: '#about' },
  { name: 'Testimonials', path: '#testimonials' },
  { name: 'Contact', path: '#contact' }
]

// Methods
const scrollToSection = (path) => {
  const element = document.querySelector(path)
  if (element) {
    const offsetTop = element.offsetTop
    window.scrollTo({
      top: offsetTop - 56,
      behavior: 'smooth'
    })
  }
}

const handleScroll = () => {
  // Update isScrolled based on scroll position
  isScrolled.value = window.scrollY > 50

  // Update active section
  const sections = navItems.map(item => item.path.substring(1))
  for (const section of sections) {
    const element = document.getElementById(section)
    if (element) {
      const rect = element.getBoundingClientRect()
      if (rect.top <= 100 && rect.bottom >= 100) {
        activeSection.value = section
        break
      }
    }
  }
}

// Lifecycle Hooks
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.navbar {
  transition: all 0.3s ease;
  background-color: transparent !important;
}

.navbar-scrolled {
  background-color: rgba(33, 37, 41, 0.9) !important;
  backdrop-filter: blur(10px);
}

.nav-link {
  color: white !important;
  font-size: 16px;
  font-weight: 600;
  margin: 0 0.5rem;
  transition: color 0.3s ease;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.nav-link:hover {
  color: #ffc107 !important;
}

.nav-link.active {
  color: #ffc107 !important;
}

.navbar-toggler {
  border-color: rgba(255, 255, 255, 0.5);
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%28255, 255, 255, 0.7%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}
</style>
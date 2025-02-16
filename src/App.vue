<!-- src/App.vue -->
<template>
  <div id="app">
    <navbar/>
    <router-view />
  </div>
</template>

<script setup>
import Navbar from "@/components/home/Navbar.vue";
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');

:root {
  --primary-yellow: #FFE31F;
  --text-light: #FFFFFF;
  --text-dark: #333333;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  min-height: 100vh;
  background-color: #000000 !important;
  color: var(--text-light);
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Hide scrollbar but keep functionality */
body {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

body::-webkit-scrollbar {
  display: none;
}

#app {
  min-height: 100vh;
}

section {
  overflow: hidden;
  min-height: 100vh;
  width: 100%;
}

/* Button styles */
.btn-outline-yellow {
  border: 2px solid var(--primary-yellow);
  color: var(--primary-yellow);
  transition: all 0.3s ease;
}

.btn-outline-yellow:hover {
  background-color: var(--primary-yellow);
  color: var(--text-dark);
}

/* Link styles */
a {
  text-decoration: none;
  color: var(--text-light);
  transition: color 0.3s ease;
}

a:hover {
  color: var(--primary-yellow);
}
</style>
<template>
  <div id="app">
    <navbar/>
    <router-view />
    <whatsapp-button
        phone-number="+917483567450"
        message="Need help? Chat with us!"
        pre-filled-message="Hi! I'm interested in learning more about your services."
    />
  </div>
</template>

<script setup>
import Navbar from "@/components/home/Navbar.vue";
import WhatsappButton from "@/components/home/WhatsappButton.vue";
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

#section{
  max-height: 100vh;
}

html, body {
  background-color: rgba(33, 37, 41, 1) !important;
  color: var(--text-light);
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

body::-webkit-scrollbar {
  display: none;
}

#app {
}

section {
  overflow: hidden;
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
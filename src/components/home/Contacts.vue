<template>
  <footer class="footer pt-5 pb-3 bg-dark text-white">
    <div class="container px-4">
      <div class="row mb-4">
        <div class="col-lg-6">
          <img src="/src/assets/images/TenzeeMultiSportsLogo.png" alt="Tenzee Fitness & Gym" height="40" class="me-2">
          <span class="text-warning fs-4">Tenzee MultiSports</span>
          <span class="text-white-50" style="margin-left: 10px">Fitness & Gym</span>
          <p class="mt-3">Please feel free to send us an email at <span class="text-warning fs-7">tenzeemultisports@gmail.com</span> for any additional inquiries</p>
        </div>
<!--        <div class="col-lg-6 text-lg-end">-->
<!--          <div class="social-icons mb-3">-->
<!--            <a href="#" class="social-icon">-->
<!--              <i class="fab fa-instagram"></i>-->
<!--            </a>-->
<!--            <a href="#" class="social-icon">-->
<!--              <i class="fab fa-youtube"></i>-->
<!--            </a>-->
<!--            <a href="#" class="social-icon">-->
<!--              <i class="fab fa-twitter"></i>-->
<!--            </a>-->
<!--            <a href="#" class="social-icon">-->
<!--              <i class="fab fa-facebook"></i>-->
<!--            </a>-->
<!--            <a-->
<!--                :href="whatsappLink"-->
<!--                target="_blank"-->
<!--                rel="noopener noreferrer"-->
<!--                class="social-icon"-->
<!--            >-->
<!--              <i class="fab fa-whatsapp"></i>-->
<!--            </a>-->
<!--          </div>-->
<!--        </div>-->
      </div>

      <hr class="border-secondary">

      <div class="row">
        <div class="text-lg-center mt-3 mt-lg-0 text-warning">
          <p class="mb-0">Copyright 2021 © All Rights Reserved by Tenzee MultiSports</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue'

const phoneNumber = '917483567450'
const whatsappLink = computed(() => `https://wa.me/${phoneNumber}`)
</script>

<style scoped>
.footer {
  font-size: 0.9rem;
}

.social-icons {
  display: flex;
  gap: 1rem;
  justify-content: flex-end;
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: 2px solid #fff;
  color: #fff;
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: #ffc107;
  border-color: #ffc107;
  color: #000;
}

.whatsapp-icon:hover {
  background-color: #25D366;
  border-color: #25D366;
  color: #fff;
}

@media (max-width: 768px) {
  nav {
    flex-direction: column;
    gap: 1rem !important;
  }

  .social-icons {
    justify-content: center;
    margin-bottom: 1rem;
  }
}
</style>
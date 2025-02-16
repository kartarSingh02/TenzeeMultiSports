<template>
  <div class="home">
    <section id="home">
      <HeroSection />
    </section>

    <section id="programs" class="pt-20">
      <Programs />
    </section>

    <section id="about" class="pt-20">
      <AboutUs />
    </section>

    <section id="testimonials" class="pt-20">
      <Testimonials />
    </section>

    <section id="contact">
      <Contacts />
    </section>
  </div>
</template>

<script setup>
import HeroSection from '@/components/home/HeroSection.vue'
import Programs from "@/components/home/Programs.vue";
import AboutUs from "@/components/home/AboutUs.vue";
import Testimonials from "@/components/home/Testimonials.vue";
import Contacts from "@/components/home/Contacts.vue";
import Navbar from "@/components/home/Navbar.vue";
</script>
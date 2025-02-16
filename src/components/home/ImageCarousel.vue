<!-- components/home/ImageCarousel.vue -->
<template>
  <div class="carousel relative h-full">
    <transition-group name="fade">
      <div
          v-for="(image, index) in images"
          :key="image.id"
          v-show="currentIndex === index"
          class="carousel-slide absolute inset-0"
      >
        <img
            :src="image.src"
            :alt="image.alt"
            class="w-full h-full object-cover"
        >
      </div>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'ImageCarousel',
  props: {
    images: {
      type: Array,
      required: true,
      validator: (value) => {
        return value.every(image =>
            typeof image.id !== 'undefined' &&
            typeof image.src === 'string' &&
            typeof image.alt === 'string'
        )
      }
    }
  },
  data() {
    return {
      currentIndex: 0,
      timer: null
    }
  },
  mounted() {
    this.startSlideshow()
  },
  beforeDestroy() {
    this.stopSlideshow()
  },
  methods: {
    startSlideshow() {
      this.timer = setInterval(this.nextSlide, 3000)
    },
    stopSlideshow() {
      clearInterval(this.timer)
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length
    }
  }
}
</script>

<style scoped>
.carousel-slide {
  transition: opacity 0.5s ease-in-out;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
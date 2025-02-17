<template>
  <div class="container-fluid bg-dark py-5 container mx-auto px-4">
    <div class="row g-4">
      <div class="col-lg-6 px-4">
        <div class="position-relative mb-4">
          <h1 class="display-4 text-white fw-bold position-relative">
            <span class="text-white-50">PROGRAMS</span><br/>
            POWERFUL<br/>
            WORKOUTS, UNLEASH<br/>
            YOUR POTENTIAL
          </h1>
        </div>

        <p class="text-white-50 mb-4">
          These are some of the interesting features that we offer to all our members
        </p>

        <div class="features-list mb-4">
          <div class="d-flex align-items-center mb-3">
            <i class="bi bi-check-square-fill text-warning me-3"></i>
            <span class="text-white">Strengthen And Conditioning program</span>
          </div>
          <div class="d-flex align-items-center mb-3">
            <i class="bi bi-check-square-fill text-warning me-3"></i>
            <span class="text-white">Mixed Martial Arts</span>
          </div>
          <div class="d-flex align-items-center mb-3">
            <i class="bi bi-check-square-fill text-warning me-3"></i>
            <span class="text-white">Wall Climbing</span>
          </div>
          <div class="d-flex align-items-center mb-3">
            <i class="bi bi-check-square-fill text-warning me-3"></i>
            <span class="text-white">Football</span>
          </div>
        </div>

        <button class="btn btn-outline-warning rounded-pill px-4 py-2">
          Book Now <i class="bi bi-arrow-right ms-2"></i>
        </button>
      </div>

      <div class="col-lg-6">
        <div class="row g-4">
          <div class="col-12">
            <div class="card bg-dark text-white border-0">
              <div class="row g-0">
                <div class="col-md-6">
                  <img
                      src="/src/assets/images/WallClimbing-1.jpeg"
                      alt="Weight Loss Training"
                      class="img-fluid h-100 object-fit-cover"
                  />
                </div>
                <div class="col-md-6 p-4">
                  <div class="card-body">
                    <h6 class="text-white-50 mb-2">TRAINING</h6>
                    <h2 class="card-title mb-3">Weight Loss</h2>
                    <p class="card-text text-white-50">
                      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec.
                    </p>
                    <button class="btn btn-outline-warning rounded-pill px-4">
                      Read More <i class="bi bi-arrow-right ms-2"></i>
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Training Plan Card -->
          <div class="col-12">
            <div class="card bg-warning text-dark border-0">
              <div class="row g-0">
                <div class="col-md-6 p-4">
                  <div class="card-body">
                    <h6 class="text-dark mb-2">TRAINING</h6>
                    <h2 class="card-title mb-3">Training Plan</h2>
                    <p class="card-text">
                      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit tellus, luctus nec.
                    </p>
                    <button class="btn btn-dark rounded-pill px-4">
                      Read More <i class="bi bi-arrow-right ms-2"></i>
                    </button>
                  </div>
                </div>
                <div class="col-md-6">
                  <img
                      src="/src/assets/images/BoxingWoman.jpeg"
                      alt="Training Plan"
                      class="img-fluid h-100 object-fit-cover"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <KidsProgram/>
</template>

<script setup>
import KidsProgram from "@/components/home/KidsProgram.vue";
</script>

<style scoped>
.features-list i {
  font-size: 1.2rem;
}
</style>
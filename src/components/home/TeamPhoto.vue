<template>
  <div class="overview_container">
    <div class="team-photo">
      <img src="/src/assets/images/team.jpg" alt="team"/>
    </div>
    <div class="overview_team_content">
      <h1 class="team-title">Our Team</h1>
      <p class="team-description">some description is here lorem ipsum dsas sd asda da</p>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
.overview_container{
  margin-top: 30px ;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.overview_team_content{
  margin-left: 2rem;
  justify-items: center;
  color: white;
}
.team-photo {
  min-height: 100vh;
  width: 60%;
  position: relative;
}

.team-title{
  font-size: 36px;
  font-weight: 600;
}

.team-description{
  font-size: 16px;
}


.team-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  padding-left: 2rem;
  padding-right: 2rem;
}
</style>
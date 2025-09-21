<script setup lang="ts">
  import Timer from "./components/Timer.vue"
</script>

<template>
  <div class="container">
    <div class="title">
      New Year Countdown
    </div>
    <div class="full-timer">
      <Timer label="Days"/>
      <Timer label="Hours"/>
      <Timer label="Minutes"/>
      <Timer label="Seconds"/>
    </div>
    
  </div>
</template>

<style scoped>
.container {
  height: 100vh;
  width: 100%;
  background-image: url('@/assets/background-img.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  text-align: center;
}

.title {
  font-size: 5rem;
  font-weight: bold;
}

.full-timer {
  display: flex;
  align-items: center;
  justify-content: space-around;
}
</style>

<script setup lang="ts">
  import { ref, onMounted, onUnmounted } from "vue";
  import Timer from "./components/Timer.vue";

  const newYears = "1 Jan 2026";
  const remainingDays = ref("");
  const remainingHours = ref("");
  const remainingMinutes = ref("");
  const remainingSeconds = ref("");

  function countdown(){
    const newYearsDate: Date = new Date(newYears);
    const currentDate: Date = new Date();

    const totalSeconds = (newYearsDate.getTime() - currentDate.getTime()) / 1000;

    const days = Math.floor(totalSeconds / 3600 / 24);
    const hours = Math.floor(totalSeconds / 3600) % 24;
    const minutes = Math.floor(totalSeconds / 60) % 60;
    const seconds = Math.floor(totalSeconds % 60);

    remainingDays.value = setTime(days);
    remainingHours.value = setTime(hours);
    remainingMinutes.value = setTime(minutes);
    remainingSeconds.value = setTime(seconds);
  }

  function setTime(value: number){
    return value >= 10 ? value.toString() : `0${value}`;
  }

  let timeInterval : ReturnType<typeof setInterval>;

  onMounted(() => {
    timeInterval = setInterval(countdown, 1000);
  });

  onUnmounted(() => {
    clearInterval(timeInterval);
  })
</script>

<template>
  <div class="container">
    <div class="title">
      New Year Countdown
    </div>
    <div class="full-timer">
      <Timer :count="remainingDays" label="Days"/>
      <Timer :count="remainingHours" label="Hours"/>
      <Timer :count="remainingMinutes" label="Minutes"/>
      <Timer :count="remainingSeconds" label="Seconds"/>
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

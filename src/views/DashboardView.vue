<script setup lang="ts">
import "../style.css";
import FarmCard from "../components/dashboard/FarmCard.vue";
</script>

<template>
  <div class="text-center">
    <h1>OPS Dashboard</h1>
    <p>Lorem ipsum dolor sit amet</p>
  </div>
  <div class="grid grid-cols-3 gap-2 pt-1">
    <FarmCard />
    <FarmCard />
    <FarmCard />
  </div>
</template>

<style scoped>
.grid {
  display: grid;
}

.grid-cols-3 {
  grid-template-columns: repeat(3, 1fr);
}

.text-center {
  text-align: center;
}

.gap-2 {
  gap: 1.5rem;
}
</style>

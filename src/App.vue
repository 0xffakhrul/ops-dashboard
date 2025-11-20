<script setup lang="ts">
import DashboardView from "./views/DashboardView.vue";
import DynamicDialog from "primevue/dynamicdialog";
</script>

<template>
  <main class="app">
    <DashboardView />
    <DynamicDialog />
  </main>
</template>

<style scoped>
.app {
  max-width: 100rem;
  margin-inline: auto;
  padding-top: 2rem;
}
</style>

<script setup lang="ts">
import { RouterView } from "vue-router"
</script>

<template>
  <RouterView />
</template>

<style>
@import "@/assets/base.css";

#app {
  font-weight: normal;
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}
</style>

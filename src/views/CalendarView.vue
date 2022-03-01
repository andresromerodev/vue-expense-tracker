<script setup lang="ts">
import { ref } from 'vue'
const value = ref(new Date())
</script>

<template>
  <el-header>
    <Menu />
  </el-header>
  <el-main>
    <el-row>
      <el-col>
        <el-calendar v-model="value" />
      </el-col>
    </el-row>
  </el-main>
</template>

<style scoped>
section {
  margin: 16px 0 16px 0;
}
</style>
<script lang="ts" setup>
import { ref } from 'vue'

const activeIndex = ref('1')
const handleSelect = (key: string, keyPath: string[]) => console.log(key, keyPath)
</script>

<template>
  <el-menu
    :default-active="activeIndex"
    class="el-menu-demo"
    mode="horizontal"
    @select="handleSelect"
  >
    <el-menu-item index="1">
      <router-link to="/" style="text-decoration: none;">Expense Tracker</router-link>
    </el-menu-item>
    <el-menu-item index="2">
      <router-link to="/calendar" style="text-decoration: none;">Calendar</router-link>
    </el-menu-item>
  </el-menu>
</template>

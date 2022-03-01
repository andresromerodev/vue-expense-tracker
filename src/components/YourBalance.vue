<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  income: number
  expense: number
}>()
const totalBalance = computed(() => props.income - props.expense);
</script>

<template>
  <section>
    <h1 class="title">Expense Tracker</h1>
    <h3 class="title">Your Balance</h3>
    <h2 class="title">${{ totalBalance }}</h2>
    <el-card class="box-card">
      <el-row>
        <el-col :span="11" style="text-align: center;">
          <h4 style="font-weight: bold;">Income</h4>
          <p>${{ income }}</p>
        </el-col>
        <el-divider style="height: auto;" direction="vertical" content-position="center" />
        <el-col :span="11" style="text-align: center;">
          <h4 style="font-weight: bold;">Expense</h4>
          <p>${{ expense }}</p>
        </el-col>
      </el-row>
    </el-card>
  </section>
</template>

<style scoped>
.title {
  font-weight: bold;
  margin-top: 16px;
  margin-bottom: 16px;
}
</style>

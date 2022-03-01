<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  description: string
  amount: number
}>()

const transactionClass = computed(() => props.amount >= 0 ? 'income' : 'expense')

</script>

<template>
  <el-card shadow="always" :class="transactionClass">
    <el-row>
      <div>{{ description }}</div>
      <div class="price-label">${{ amount }}</div>
    </el-row>
  </el-card>
</template>

<style scoped>
.el-card {
  margin: 16px 0 16px 0;
}

.income {
  border-right-width: 8px;
  border-right-color: green;
}

.expense {
  border-right-width: 8px;
  border-right-color: red;
}

.price-label {
  margin-left: auto;
}
</style>
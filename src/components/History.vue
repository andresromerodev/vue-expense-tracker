<script setup lang="ts">
import TransactionCard from './TransactionCard.vue';
defineProps<{
  transactions?: any[]
}>()
</script>

<template>
  <div>
    <h3>History</h3>
    <el-row :gutter="24">
      <el-col>
        <transaction-card
          v-for="transaction in transactions"
          :description="transaction.description"
          :amount="transaction.amount"
        />
      </el-col>
    </el-row>
  </div>
</template>

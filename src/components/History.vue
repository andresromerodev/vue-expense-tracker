<script setup lang="ts">
import TransactionCard from './TransactionCard.vue'
defineProps<{
  transactions?: any[]
}>()
</script>

<template>
  <section>
    <h3>History</h3>
    <el-row :gutter="24">
      <el-col>
        <el-empty v-if="!transactions?.length" description="History is empty"></el-empty>
        <transaction-card
          v-for="transaction in transactions"
          :description="transaction.description"
          :amount="transaction.amount"
        />
      </el-col>
    </el-row>
  </section>
</template>

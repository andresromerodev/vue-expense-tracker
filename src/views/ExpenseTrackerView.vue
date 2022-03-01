<script setup lang="ts">
import { reactive, ref } from 'vue'

import YourBalance from "../components/YourBalance.vue"
import History from "../components/History.vue"
import TransactionForm from "../components/TransactionForm.vue"

const balance = reactive({ income: 0, expense: 0 })
const transactions = ref<any[]>([])

// TODO: Add typings to avoid casting to number
const addTransaction = (transaction: any) => {
  transactions.value.push(transaction)
  if (transaction.amount > 0) {
    balance.income += Number(transaction.amount)
  } else {
    // Convert from negative to positive number
    balance.expense += Number(Math.abs(transaction.amount))
  }
}
</script>

<template>
  <el-container>
    <el-main>
      <el-row>
        <el-col>
          <YourBalance class="section" :income="balance.income" :expense="balance.expense" />
          <History class="section" :transactions="transactions" />
          <TransactionForm class="section" @add-transaction="addTransaction" />
        </el-col>
      </el-row>
    </el-main>
  </el-container>
</template>

<style scoped>
section {
  margin: 16px 0 16px 0;
}
</style>
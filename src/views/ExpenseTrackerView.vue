<script setup lang="ts">
import { reactive, ref } from 'vue'

import YourBalance from "../components/YourBalance.vue"
import History from "../components/History.vue"
import TransactionForm from "../components/TransactionForm.vue"
import Navbar from "../components/Navbar.vue"

const balance = reactive({ income: 0, expense: 0 })
const transactions = ref<any[]>([])

const addTransaction = (transaction: any) => {
  transactions.value.push(transaction)
  if (transaction.amount > 0) {
    balance.income += Number(transaction.amount)
  } else {
    balance.expense += Number(Math.abs(transaction.amount))
  }
}
</script>

<template>
  <el-header>
    <navbar />
  </el-header>
  <el-main>
    <el-row>
      <el-col>
        <your-balance
          class="section"
          :income="balance.income"
          :expense="balance.expense"
        />
        <history class="section" :transactions="transactions" />
        <transaction-form class="section" @add-transaction="addTransaction" />
      </el-col>
    </el-row>
  </el-main>
</template>

<style scoped>
section {
  margin: 16px 0 16px 0;
}
</style>
<script setup lang="ts">

import { ref } from 'vue'

import YourBalance from "../components/YourBalance.vue";
import History from "../components/History.vue";
import TransactionForm from "../components/TransactionForm.vue";

const transactions = ref<any[]>([{ description: "Book", amount: 20 }]);

const addTransaction = (transaction: any) => transactions.value.push(transaction);

</script>

<template>
  <el-container>
    <el-main>
      <el-row>
        <el-col :span="10">
          <YourBalance class="section" />
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
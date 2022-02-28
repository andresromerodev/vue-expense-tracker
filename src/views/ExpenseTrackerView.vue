<script setup lang="ts">
import YourBalance from "../components/YourBalance.vue";
import History from "../components/History.vue";
import AddTransaction from "../components/AddTransaction.vue";
import { ref } from 'vue'

const transactions = ref<any[]>([{ description: "Flower", amount: 20 }]);

const handleAddTransaction = (transaction: any) => {
  console.log('Transaction: ', transaction);
  transactions.value.push(transaction);
}

</script>

<template>
  <el-container>
    <el-main>
      <el-row>
        <el-col :span="10">
          <your-balance class="component" />
          <history class="component" :transactions="transactions" />
          <add-transaction @handle-add-transaction="handleAddTransaction" class="component" />
        </el-col>
      </el-row>
    </el-main>
  </el-container>
</template>

<style scoped>
.component {
  margin: 16px 0 16px 0;
}
</style>
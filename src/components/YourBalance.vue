<script setup lang="ts"></script>

<template>
  <section>
    <h1>Expense Tracker</h1>
    <h3 class="title">Your Balance</h3>
    <h2 class="title">$420.00</h2>
    <el-card class="box-card">
      <el-row>
        <el-col :span="11" style="text-align: center;">
          <h4>Income</h4>
          <p>$450</p>
        </el-col>
        <el-divider style="height: auto;" direction="vertical" content-position="center" />
        <el-col :span="11" style="text-align: center;">
          <h4>Expense</h4>
          <p>$30</p>
        </el-col>
      </el-row>
    </el-card>
  </section>
</template>

<style scoped>
.title {
  margin-top: 16px;
  margin-bottom: 16px;
}
</style>

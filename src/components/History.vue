<script setup lang="ts">

</script>

<template>
  <div>
    <h3>History</h3>
    <el-row :gutter="24">
      <el-col :span="24">
        <el-card shadow="always" class="income">
          <el-row>
            <div>Flower</div>
            <div class="price-label">$20</div>
          </el-row>
        </el-card>
        <el-card shadow="always" class="expense">
          <el-row>
            <div>Movie</div>
            <div class="price-label">$30</div>
          </el-row>
        </el-card>
        <el-card shadow="always" class="income">
          <el-row>
            <div>Book</div>
            <div class="price-label">$40</div>
          </el-row>
        </el-card>
      </el-col>
    </el-row>
  </div>
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
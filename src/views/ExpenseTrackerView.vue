<script setup lang="ts">
import YourBalance from "../components/YourBalance.vue";
import History from "../components/History.vue";
</script>

<template>
  <el-container>
    <el-main>
      <el-row>
        <el-col :span="10">
          <your-balance class="component" />
          <history class="component" />
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
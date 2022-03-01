<script setup lang="ts">
import { reactive, defineEmits, computed } from 'vue'

const emit = defineEmits(['addTransaction'])

const form = reactive({
  description: '',
  amount: 0
})

const onSubmit = () => emit('addTransaction', { ...form })

const submitDisabled = computed(
  () => !form.description || !form.amount || form.amount === 0
)

</script>

<template>
  <section>
    <h3>Add New Transaction</h3>
    <el-form class="transaction-form" ref="formRef" :model="form" label-position="top">
      <el-form-item label="Description">
        <el-input v-model="form.description" placeholder="Enter text..."></el-input>
      </el-form-item>
      <el-form-item label="Amount">
        <el-input v-model="form.amount"></el-input>
      </el-form-item>
      <el-form-item size="large">
        <el-button type="primary" @click="onSubmit" :disabled="submitDisabled">Create</el-button>
      </el-form-item>
    </el-form>
  </section>
</template>

<style scoped>
.transaction-form {
  margin: 16px 0 16px 0;
}

button {
  width: 100%;
  margin: 10px 0;
  display: block;
}
</style>
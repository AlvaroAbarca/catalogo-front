<template>
  <el-row class="row-bg" justify="center">
    <el-col :span="16">
      <span>{{ welcomeMessage }}</span>
    </el-col>
    <el-col :span="16">
      <span>{{ description }}</span>
    </el-col>
    <el-col :span="16">
      <span>{{ delivery }}</span>
    </el-col>
    <el-col :span="16">
      <span>{{ paymentMethods }}</span>
    </el-col>
    <el-col :span="16">
      <span>{{ attendedBy }}</span>
    </el-col>
  </el-row>
</template>
<script setup lang="ts">
  const props = defineProps({
    welcomeMessage: { type: String, required: true },
    description: { type: String, required: true },
    delivery: { type: String, required: true },
    paymentMethods: { type: String, required: true },
    attendedBy: { type: String, required: true },
  });
</script>

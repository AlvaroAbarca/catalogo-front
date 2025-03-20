<template>
  <el-row class="icon-row">
    <el-col :span="2" class="icon-col">
      <component :is="icon" class="logo" />
    </el-col>
    <el-col :span="22" class="text-col">
      <el-link v-if="link !==''" :href="link" target="_blank">
        <span class="text-logo">{{ text }}</span>
      </el-link>
      <span class="text-logo" v-else>{{ text }}</span>
    </el-col>
  </el-row>
</template>

<script setup lang="ts">
defineProps({
  icon: {
    required: true
  },
  text: {
    type: String,
    required: true
  },
  link: {
    type: String,
    required: false,
    default: ''
  }
});
</script>

<style scoped>
.icon-row {
  display: flex;
  align-items: center;
}

.icon-col {
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo {
  width: 36px;
  height: 36px;
}

.text-col {
  display: flex;
  align-items: center;
}

.text-logo {
  margin-left: 10px;
  font-size: 16px;
}
</style>

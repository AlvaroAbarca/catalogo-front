<script setup lang="ts">
import { ref } from 'vue'
import type { TabsPaneContext } from 'element-plus'
import SingleProduct from './SingleProduct.vue';
import SingleProductWip from './SingleProductWip.vue';

const activeName = ref('first')

const handleClick = (tab: TabsPaneContext, event: Event) => {
  console.log(tab, event)
}
</script>
<template>
  <el-tabs v-model="activeName" class="demo-tabs" @tab-click="handleClick">
    <el-tab-pane label="User" name="first">
      <SingleProduct />
      <SingleProductWip />
      <!-- <div w="full" py="4">
      </div> -->
        <!-- <el-row >
        <el-col :span="12" :offset="6">
        </el-col>
      </el-row> -->
    </el-tab-pane>
    <el-tab-pane label="Config" name="second">Config</el-tab-pane>
    <el-tab-pane label="Role" name="third">Role</el-tab-pane>
    <el-tab-pane label="Task" name="fourth">Task</el-tab-pane>
  </el-tabs>
</template>
<style>
/* .demo-tabs > .el-tabs__content { */
  /* width: fit-content;
  height: fit-content; */
  /* padding: 32px;
  color: #6b778c;
  font-size: 32px;
  font-weight: 600; */
/* } */
</style>

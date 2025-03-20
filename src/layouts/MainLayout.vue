<script setup lang="ts">
import NavBar from './NavBar.vue';

</script>

<template>
  <el-container>
    <NavBar />
    <slot></slot>
    <!-- <span>slot</span> -->
    <!-- <el-main>
    </el-main> -->
    <el-footer>
      <span>Footer</span>
    </el-footer>
  </el-container>
</template>

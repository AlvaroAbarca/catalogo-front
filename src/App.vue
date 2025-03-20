<script setup lang="ts">
import { RouterView } from 'vue-router'
import MainLayout from './layouts/MainLayout.vue'
import "./assets/utilities.css"
import "./assets/main.css"
import "./assets/index.scss"
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->
  <MainLayout>
    <RouterView />
    <!-- <el-row class="row-bg" justify="center">
      <el-col :span="22">
      </el-col>
    </el-row> -->
    <!-- <RouterView /> -->
  </MainLayout>
  <!-- <el-config-provider namespace="ep">
  </el-config-provider> -->
</template>

<template>
  <el-row>
    <el-col :span="3" :offset="2">
      <el-image class="product-image"
        src="https://storage.googleapis.com/la-lista-de.appspot.com/tiendas/thumb_29922da8-66f1-4fba-b3f2-5b1283b2facb" />
    </el-col>
    <el-col :span="6" class="product--data">
      <el-row>
        <el-col :span="24">
          <span class="product--name">Nombre del producto</span>
        </el-col>
        <el-col :span="24">
          <span>Descripción del producto</span>
        </el-col>
        <el-col :span="24">
          <span class="product--price">Precio: $3.990</span>
        </el-col>
      </el-row>
    </el-col>
    <el-col :span="2" :offset="8" class="product--add">
      <el-input-number
        v-if="amount > 0"
        v-model="amount"
        :min="0" :max="10"
        @change="handleChange"
        step-strictly
        :disabled="amount === 0"
        />
      <el-button v-else type="primary" @click="amount++" >Agregar</el-button>
    </el-col>
    <el-col :span="24">
      <el-divider />
    </el-col>
  </el-row>
</template>
<script setup lang="ts">
import { ref } from 'vue';

const amount = ref(0);
const handleChange = (value: number) => {
  console.log(value);
}
</script>
<style>
  .product-image {
    width: 125px;
    height: 125px;
  }
  .product-image:hover {
    cursor: pointer;
  }
  .product-image:active {
    transform: scale(0.95);
  }
  .product-image:focus {
    outline: none;
  }
  .product--name {
    font-size: var(--el-font-size-large);
    margin-top: 10px;
    margin-bottom: 10px;
  }
  .product--description {
    font-size: var(--el-font-size-medium);
  }
  .product--price {
    font-size: var(--el-font-size-medium);
    font-weight: bold;
    color: var(--el-color-primary);
  }
  /* .product--data, */
  .product--add {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>

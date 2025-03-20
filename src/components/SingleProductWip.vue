<template>
  <section class="product-card">
    <header class="product-header">
      <el-row justify="space-between" align="middle">
        <!-- Product Image -->
        <el-col :span="4">
          <el-image class="product-image"
            src="https://storage.googleapis.com/la-lista-de.appspot.com/tiendas/thumb_29922da8-66f1-4fba-b3f2-5b1283b2facb"
            fit="cover" alt="Product Image" />
        </el-col>

        <!-- Product Details -->
        <el-col :span="12" class="product-details">
          <h2 class="product-name">Nombre del producto</h2>
          <p class="product-description">Descripción del producto</p>
          <p class="product-price">Precio: $3.990</p>
        </el-col>

        <!-- Add to Cart Section -->
        <el-col :span="6" class="product-actions">
          <div v-if="amount > 0" class="quantity-selector">
            <el-input-number v-model="amount" :min="0" :max="10" @change="handleChange" step-strictly
              :disabled="amount === 0" />
          </div>
          <el-button v-else type="primary" class="add-to-cart-button" @click="amount++">
            Agregar
          </el-button>
        </el-col>
      </el-row>
    </header>

    <el-divider />
    <!-- <footer class="product-footer">
    </footer> -->
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const amount = ref(0);

const handleChange = (value: number) => {
  console.log('Updated quantity:', value);
};
</script>

<style scoped lang="scss">
// Variables for consistent styling
$primary-color: var(--el-color-primary);
$text-color: var(--el-text-color-primary);
$font-family: var(--el-font-family);

.product-card {
  padding: 16px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  margin-bottom: 24px;

  @media (max-width: 768px) {
    padding: 12px;
  }
}

.product-header {
  display: flex;
  flex-direction: column;
  gap: 16px;

  @media (max-width: 768px) {
    flex-direction: column;
    align-items: center;
  }
}

.product-image {
  width: 125px;
  height: 125px;
  border-radius: 8px;
  object-fit: cover;
  transition: transform 0.2s ease-in-out;

  &:hover {
    cursor: pointer;
    transform: scale(1.05);
  }

  &:active {
    transform: scale(0.95);
  }

  &:focus {
    outline: none;
  }
}

.product-details {
  display: flex;
  flex-direction: column;
  gap: 8px;

  .product-name {
    font-size: var(--el-font-size-large);
    font-weight: bold;
    color: $text-color;
    margin: 0;
  }

  .product-description {
    font-size: var(--el-font-size-medium);
    color: var(--el-text-color-secondary);
    margin: 0;
  }

  .product-price {
    font-size: var(--el-font-size-medium);
    font-weight: bold;
    color: $primary-color;
    margin: 0;
  }
}

.product-actions {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 8px;

  .quantity-selector {
    width: 100%;
  }

  .add-to-cart-button {
    width: 100%;
  }
}

.product-footer {
  margin-top: 16px;
}
</style>

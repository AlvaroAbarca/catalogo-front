<script setup lang="ts">
import { ref } from 'vue'
import type { TabsPaneContext } from 'element-plus'

import MainCarrousel from '@/components/MainCarrousel.vue';
import CategoryTabs from '@/components/CategoryTabs.vue';
import StoreInfo from '@/components/StoreInfo.vue';
import ContactData from '@/components/ContactData.vue';

const activeName = ref('first')

const handleClick = (tab: TabsPaneContext, event: Event) => {
  console.log(tab, event)
}
</script>

<template>
  <main>
    <el-row class="row-bg" justify="center">
      <el-col :xs="24" :sm="24" :md="24" :lg="22" :xl="22">
        <MainCarrousel :images="[]" />
      </el-col>
      <el-col :xs="24" :sm="24" :md="24" :lg="22" :xl="22">
        <el-card class="box-card">
          <!-- <template #header>
            <div class="card-header">
              <span>Card name</span>
            </div>
          </template> -->
          <StoreInfo welcomeMessage="Bienvenidos a La casa del ahorro"
            description="Sin tener que salir de casa, sin largas esperas y sin filas. Haz tu pedido hasta las 12:00PM para recibirlo el mismo día. Pedido mínimo $10.000"
            delivery="Entrega: 🏡 MELIPILLA: LUNES - MARTES - MIERCOLES - VIERNES - SABADO. 🌇 SANTIAGO: LUNES - JUEVES."
            paymentMethods="Medios de pago: Transferencias y efectivo" attendedBy="Atendido por Camila" />
          <el-divider />
          <!-- two colums -->
          <ContactData
            qrLink="https://la-lista-de.appspot.com.storage.googleapis.com/tiendas/frutasyverdurasmelipilla/QR-frutasyverdurasmelipilla.png"
            storeName="Store Name" />
          <el-row>
            <el-col :span="24">
              <CategoryTabs />
            </el-col>
          </el-row>
        </el-card>
      </el-col>
    </el-row>
  </main>
</template>
<style scoped>
.demonstration {
  color: var(--el-text-color-secondary);
}
</style>


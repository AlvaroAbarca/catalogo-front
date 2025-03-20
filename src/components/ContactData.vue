<template>
  <el-row justify="center">
    <el-col :span="12">
      <el-row justify="end" align="middle">
        <el-col :span="16">
          <el-image class="qr" :src="qrLink" />
        </el-col>
        <el-col :span="16">
          <span>{{ storeName }}</span>
        </el-col>
      </el-row>
    </el-col>
    <el-col :span="12">
      <IconRow :icon="IconInstagram" text="Instagram" />
      <IconRow :icon="IconWhatsapp" text="whatsapp" />
      <IconRow :icon="IconEmail" text="email" />
      <IconRow :icon="IconMapMarker" text="map-marker" />
      <IconRow :icon="IconLink" text="link" />
    </el-col>
  </el-row>
</template>
<script setup lang="ts">

import IconRow from './icons/IconRow.vue';

import IconEmail from './icons/IconEmail.vue';
import IconInstagram from './icons/IconInstagram.vue';
import IconLink from './icons/IconLink.vue';
import IconMapMarker from './icons/IconMapMarker.vue';
import IconWhatsapp from './icons/IconWhatsapp.vue';

defineProps({
  qrLink: { type: String, required: true },
  storeName: { type: String, required: true },
});
</script>
<style>

.qr {
  width: 150px;
  height: 150px;
}
</style>

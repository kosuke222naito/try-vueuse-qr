<script setup lang="ts">
import { ref } from "vue";

import { useMouse, usePreferredDark } from "@vueuse/core";
import { useQRCode } from '@vueuse/integrations/useQRCode';

const { x, y } = useMouse();
const isDark = usePreferredDark();

const text = ref("text-to-encode");
const qrcode = useQRCode(text)
</script>

<template>
  {{ x }}, {{ y }}
  {{ isDark }}

  <div>
    <input v-model="text" type="text" />
    <img :src="qrcode" alt="QR Code" />
  </div>

</template>

<style scoped></style>

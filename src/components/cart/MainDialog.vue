<script setup>
import BtnIconRounded from "../common/BtnIconRounded.vue";

import Tabs from "./Tabs.vue";

import Dialog from "primevue/dialog";

defineProps(["toggleCart", "totalCost"]);

const emits = defineEmits(["closeCart"]);
</script>
<template>
  <Dialog :visible="toggleCart" header="Header" :closable="false">
    <template #header>
      <div class="w-full flex flex-col">
        <div
          class="w-full max-w-bd-sm mx-auto p-4 flex items-center justify-between"
        >
          <div
            class="text-md text-primary dark:text-primary-dark font-ssp font-bold"
          >
            $ {{ totalCost }}
          </div>
          <BtnIconRounded icon="pi pi-times" @click="emits('closeCart')" />
        </div>
      </div>
    </template>
    <Tabs />
  </Dialog>
</template>

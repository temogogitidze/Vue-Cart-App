<script setup>
import { ref } from "vue";

import useCartStore from "../../stores/cart";
import CartToggleBtn from "./CartToggleBtn.vue";
import MainDialog from "./MainDialog.vue";

const cartStore = useCartStore();
const toggleCart = ref(false);
</script>

<template>
  <div
    class="sticky left-100 bottom-0 z-10 p-4 pb-20"
    @click="toggleCart = true"
  >
    <CartToggleBtn :total-items="cartStore.totalItems" />
    <MainDialog
      :total-cost="cartStore.totalCost"
      :toggleCart="toggleCart"
      @closeCart="toggleCart = false"
    />
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

// import Badge from "../Common/Badge.vue";

const props = defineProps(["totalItems"]);

const cartRef = ref(null);

watch(
  () => props.totalItems,
  () => {
    cartRef.value.classList.add("animate__heartBeat");
  }
);

const removeTadaClass = () => {
  cartRef.value.classList.remove("animate__heartBeat");
};
</script>
<template>
  <div
    id="animation-box"
    class="inline-block cursor-pointer animate__animated"
    @animationend="removeTadaClass"
    ref="cartRef"
  >
    <!-- <Badge
      :value="totalItems"
      class="toggle-btn pi pi-shopping-cart border-2 border-secondary rounded-full text-lg text-white p-4"
    /> -->
  </div>
</template>

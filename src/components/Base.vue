<template>
  <div v-if="isBlack" class="baseBeverage blackTea"></div>
  <div v-else-if="isGreen" class="baseBeverage greenTea"></div>
  <div v-else-if="isCoffee" class="baseBeverage coffee"></div>
</template>

<script setup lang="ts">
type Props = {
  isBlack: boolean;
  isGreen: boolean;
  isCoffee: boolean;
}
defineProps<Props>();
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
.greenTea {
  background-color: #C8E6C9;
}
.blackTea {
  background-color: #8B4513;
}
.coffee {
  background-color: #6F4E37;
}
</style>

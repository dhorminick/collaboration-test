<template>
  <div class="bg-white rounded-lg shadow p-5 flex flex-col gap-2 border border-orange-200">
    <div class="text-lg font-bold text-orange-600">{{ name }}</div>
    <div class="text-gray-600">Category: {{ category }}</div>
    <div class="text-gray-800 font-semibold">${{ price }}</div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  category: String,
  price: Number
})
</script>

<style lang="scss" scoped></style>

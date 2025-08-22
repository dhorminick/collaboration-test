<template>
  <div class="flex flex-col gap-[4px] mt-[20px]">
    <label :for="id" class="font-semibold">{{ label }}</label>
    <input :type="type" :id="id" :placeholder="pc" :required="required" class="rounded-[30px] border border-gray-400 px-4 py-2 focus:outline-none focus:ring-1 focus:ring-hover focus:border-hover">
  </div>
</template>

<script setup>
const props = defineProps({
  label: '',
  type:'',
  id:'',
  pc:'', 
  required:false
})

</script>

<style lang="scss" scoped>


</style>
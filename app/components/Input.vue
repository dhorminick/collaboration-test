<template>
    <div>
      <label :for="id">{{ label }}</label>
      <input :type=type :id=id :placeholder=pc :required=required class="rounded-md">
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
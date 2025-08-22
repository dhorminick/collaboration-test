<template>
  <div class="mt-6">
    <button 
      :type="type" 
      @click="$emit('clicked')"
      class="w-full bg-button text-white py-2 rounded-[30px] hover:bg-hover transition"
    >
      {{ buttonName }}
    </button>
  </div>
</template>


<script setup>
const emit = defineEmits(["clicked"])


const props = defineProps({
  type:'',
  buttonName:''
})
</script>

<style lang="scss" scoped>

</style>
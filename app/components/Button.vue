<template>
  <div>
    <button :type="type" @click="$emit('clicked')">
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
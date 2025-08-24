<template>
    <div>
        <input :type="inputType ?? 'text'" :class="inputStyle"/>
    </div>
</template>

<script setup>
    const props = defineProps(["inputType"])

</script>

<style lang="scss" scoped>

</style>